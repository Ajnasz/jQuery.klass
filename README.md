jQuery.klass
==============

A simple class implementation for jQuery - based on MooTools 1.11 with added
git patches and modifications (mostly for runtime inspectors).

Exported functions
------------------

  + $.klass = creates a class
  + $.klass.merge = merges two objects into a third one
  + $.klass.setClassPool = setup your global classes container here (see code for examples)
  + $.klass.getClasses = returns the classpool you set above
  + $.klass.getInstances = get all the instances
  + $.klass.getInstancesByClass = get all the instances neatly grouped by their classnames
  + $.klass.getFirstInstanceOf = get the first instance of a given classname
  + $.klass.getLastInstanceOf = get the last instance of a given classname
  + $.klass.isClassInstanciated = has this class been instanciated? returns a bool

Some examples
-------------
```javascript
var Animal = new $.klass({
	initialize: function(age){
		this.age = age;
	}
});

var Cat = Animal.extend({ // same as Cat = $.klass(Animal, {....
	initialize: function(name, age){
		this.parent(age);
		this.name = name;
	}
});

var myCat = new Cat('Micia', 20);
alert(myCat.name); //alerts 'Micia'
alert(myCat.age); //alerts 20
```