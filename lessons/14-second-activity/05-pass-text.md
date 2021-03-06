К настоящему моменту мы запрограммировали актив­ность MainActivity так, чтобы она запуска­ла ReceiveActivity при щелчке на кнопке Send. Теперь необходимо обеспечить передачу введенного текста из MainActivity в ReceiveActivity, чтобы активность ReceiveActivity могла вывести полученный текст.

Для этого необходимо:
- изменить макет activity_receive.xml так, чтобы он мог использоваться для вывода текста. Сейчас он представляет пустой макет.
- обновить активность MainActivity.java, чтобы она получала введенный пользователем текст. Этот текст должен быть добавлен в интент перед его отправкой.
- обновить код ReceiveActivity.java, чтобы он выводил текст, отправленный в интенте.

В макете activity_receive.xml необходимо внести пару изменений.
Прежде всего необходимо добавить компонент TextView и назначить ему идентификатор. Идентификаторы должны назначаться всем компонентам графического интерфейса, с которыми вы хотите работать в коде активности, — иден­тификатор используется для обращения к компоненту из кода Java. Также уберем текст по умолчанию.


Вы уже видели, как создать новый интент командой
```
  Intent intent = new Intent(this, Target.class);
```
В интент также можно добавить дополнительную информацию, которая должна передаваться получателю. В этом случае актив­ность, получившая интент, сможет на него как­то среагировать. Для этого используется метод putExtra()

```
  intent.putExtra("сообщение", значение);
```
где сообщение — имя ресурса для передаваемой информации, а значение — само значение. Перегрузка метода putExtra() позволяет передавать значение многих возможных типов. Например, это может быть примитив (boolean или int), массив примитивов или String. Многократные вызовы putExtra() позволяют включить в интент несколько экземпля­ров дополнительных данных. Если вы решите действовать так, проследите за тем, чтобы каждому экземпляру было присвоено уникальное имя.


Получение дополнительной информацию из интента

Когда Android приказывает ReceiveActivity запуститься, активность должна каким­-то образом получить дополнительную информацию, которая была отправлена MainActivity системе Android в интенте.

Существует удобный метод - getIntent();

getIntent() возвращает интент, запустивший активность; из полу­ченного интента можно прочитать любую информацию, отправленную вместе с ним. 

Конкретный способ чтения зависит от типа отправленной информации. Например, если вы знаете, что интент включает строко­вое значение с именем “message”, используйте следующий вызов:
```
  Intent intent = getIntent();
  String string = intent.getStringExtra("message");
```
Конечно, из интента можно читать не только строковые значения. Например, вызов
```
  int intNum = intent.getIntExtra("name", default_value);
```
может использоваться для получения значения int с именем name. Параметр default_value указывает, какое значение int должно ис­пользоваться по умолчанию.

