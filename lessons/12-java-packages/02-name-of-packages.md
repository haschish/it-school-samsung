Классы стандартной библиотеки Java находятся в пакетах с префиксами java. и javax.

Для пользовательских пакетов в Java существует следующее соглашение. Пакеты принято называть в соответствии с доменными именами компаний, продукта или проекта в рамках которых этот код написан.

Код который пишут в компании Google будет в пакетах начинающиеся на com.google.
Внутри уже можно заводить произвольную структуру под пакеты.

Смысл правила при использовании доменных имен при именовании пакетов состоит в том, чтобы снизить вероятность коллизий имен классов написанных разными людьми. 
Благодаря этому можно найти в интернете какую-то java-библиотеку, скачать jar-ник, подключить к своей программе и не беспокоится о том что классы из этой библиотеки будут конфликтовать с классами вашей программы или классами других подключенных библиотек.

Помимо задания области видимости и предотвращения коллизий имен, пакеты могут служить для группировки связанных классов внутри программы. 

Например, все классы относящиеся к ядру программы, могут быть собраны в пакете core. Разнообразные утилитные классы в пакете util. Подключаемые модули в пакете plugins.
