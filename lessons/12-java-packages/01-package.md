Если следовать духу ООП наша программа должна быть разбита на маленькие классы, каждый из которых слабо связан с остальными и сильно специализирован, т.е. решает одну задачу, а не делает все сразу.

Когда количество классов в нашей программе переваливает за десяток, то возникает задача как-то наши классы упорядочивать и структурировать. Для этого в Java есть пакеты.

Принадлежность класса пакету обозначается директивой package в самом начале с исходным кодом класса. Обычно эта директива идет первой строчкой. 

```
  package org.itcube;

  puclic class Hello {
  }
```

org.itcube - имя пакета. C учетом того, что класс Hello находиться в этом пакете. Полное имя класса будет org.itcube.Hello

Если в файле несколько классов, то директива package действует на все.

В отсутствии директивы класс принадлежит пакету по умолчанию, который не имеет имени. И полное имя класса будет совпадать с коротким именем.

В Java принято раскладывать исходники в соответствии с их пакетами. Исходный код класса Hello должен находиться в файле /org/itcube/Hello.java

Тоже справедливо и скомпилированного байт-кода, class-файлы будут разложенны компилятором по директориям в соответствии с их пакетами. 

Это важно для виртуальной машины, которая, когда ей потребуется загрузить класс с полным именем org.itcube.Hello, будет искать его строго в файле /org/itcube/Hello.class и нигде больше.

Пакет задает область видимости класса. Другие классы этого же пакета могут обращаться к классу Hello по его короткому имени.

Классы из других пакетов должны ссылаться на класс Hello по его полному имени. Либо использовать директиву import.

```
  import org.itcube.Hello;

  import org.itcube.*;
```

Импортировать можно конкретные классы, либо все содержимое пакета сразу.

Такие классы как Integer и прочие обертки, System, Math с которыми мы уже имели дело находяться в стандартном пакете java.lang

Однако импортировать их нам не приходилось. Это потому, что в любой Java программе подразумевается неявный импорт всех классов из пакета java.lang и классы этого пакета всегда доступны по их коротким именам.

Есть еще одна форма директивы import - import static, которая позволяет импортировать  статические поля и методы. Т.е. в тексте программы можно будет обращаться к ним не указывая имя класса. 

Директива import служит только одной цели, она позволяет в исходном коде вашей программы ссылаться на импортированные классы по их коротким именам. Никакой подстановки тела импортированного класса в ваш файл не происходит. 