---
id: 587d7db1367417b2b2512b86
title: 重置一个继承的构造函数属性
challengeType: 1
forumTopicId: 301324
---

# --description--

当一个对象从另一个对象那里继承了其`原型`，那它也继承了`父类`的 constructor 属性。

请看下面的举例：

```js
function Bird() { }
Bird.prototype = Object.create(Animal.prototype);
let duck = new Bird();
duck.constructor // function Animal(){...}
```

但是`duck`和其他所有`Bird`的实例都应该表明它们是由`Bird`创建的，而不是由`Animal`创建的。为此，你可以手动把`Bird`的 constructor 属性设置为`Bird`对象：

```js
Bird.prototype.constructor = Bird;
duck.constructor // function Bird(){...}
```

# --instructions--

修改你的代码，使得`duck.constructor`和`beagle.constructor`返回各自的构造函数。

# --hints--

`Bird.prototype`应该是`Animal`的一个实例。

```js
assert(Animal.prototype.isPrototypeOf(Bird.prototype));
```

`duck.constructor`应该返回`Bird`。

```js
assert(duck.constructor === Bird);
```

`Dog.prototype`应该是`Animal`的一个实例。

```js
assert(Animal.prototype.isPrototypeOf(Dog.prototype));
```

`beagle.constructor`应该返回`Dog`。

```js
assert(beagle.constructor === Dog);
```

# --solutions--

