В примере с геометрическими фигурами есть два неприятных момента:

- мы можем сделать экземпляр класса Shape, и несмотря на то, что код останется рабочим, концептуально это неверно. Ведь программа работает с конкретными фигурами, а не обобщенными.
- в классах описывающие фигуры мы можем не переопределить метод getArea(), что так же сохранит нашу программу рабочей, но приведет к ошибке в логике работы программы. Ведь если есть конкретная фигура, то и площадь у нее должна быть, а нам будет возвращаться NaN, вне зависимости от свойств фигуры. Этот метод программист может просто забыть переопределить, и в программе появиться ошибка, о которой, скорее всего, узнает уже пользователь.

Для решения этих проблемных мест существует понятие абстрактный класс.

Чтобы объявить класс абстрактным используется ключевое слово abstract
```
public abstract class Shape {
  ...
}
```
Если класс объявлен как абстрактный, это означает, что нельзя создавать его экземпляры. Создать можно только экземпляр класса наследника, не являющегося абстрактным.

В абстрактном классе может быть все тоже, что и в обычном, поля, конструкторы и методы. Но некоторые методы могут быть абстрактными, т.е. без реализации. 

В данном классе Shape, нужно сделать абстракстным метод getArea(), поскольку на данном уровне иерархии наследования, мы не можем предоставить никакую разумную реализацию.
```
public abstract double getArea();
```

Все необстрактные классы наследники, должны предоставить реализацию этого метода. Наличие абстрактного метода в неабстрактном классе приведет к ошибке компиляции. 

Итак, абстрактные классы решают сразу две задачи. С одной стороны они определяют набор публичных методов, т.е. по сути внешний контракт данного класса. С другой стороны они могут содержать непубличные поля и методы, т.е. содержать детали реализации.
