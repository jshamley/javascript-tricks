
# JavaScript Tricks

Jeff Shamley | @jeff_shamley | https://jeffshamley.com

---

# Caveats

---
# IIFE
#### Immediately Invoked Function Expression

```
(function() {
  var vehicle = 'car';
  console.log(vehicle);
  // 'car'
})();
console.log(vehicle);
// Uncaught ReferenceError: vehicle is not defined
```
 <!-- .element: class="fragment" -->
---

# Block Scope

___
# Block Scope
```
if (true) {
  var vehicle = 'car';
} else {
  var vehicle = 'truck';
}
console.log(vehicle);
// 'car'
```
___
# Block Scope
```
if (true) {
  let vehicle = 'car';
} else {
  let vehicle = 'truck';
}
console.log(vehicle);
// Uncaught ReferenceError: vehicle is not defined
```
```
let vehicle;
if (true) {
  vehicle = 'car';
} else {
  vehicle = 'truck';
}
console.log(vehicle);
// 'car'
```
 <!-- .element: class="fragment" -->
___
# Block Scope
```
if (true) {
  let vehicle = 'car';
  console.log(vehicle);
  // 'car'
} else {
  let vehicle = 'truck';
  console.log(vehicle);
  // 'truck'
}
```
---

# Use Strict

___
# Use Strict
```
var vehicle;
vehcile = 'car';
console.log(vehicle);
// undefined
console.log(vehcile);
// 'car'
```
___
# Use Strict
```
var vehicle;
(function() {
  vehcile = 'car';
})();
console.log(vehcile);
// 'car'
```
___
# Use Strict
```
'use strict';
var vehicle;
vehcile = 'car';
// Uncaught ReferenceError: vehcile is not defined
```
___
# Use Strict
```
// non-strict code
(function() {
  'use strict';
  // strict code
})();
// non-strict code
```
---

# Double Negation

___
# Double Negation

```
if (obj && obj.someProperty) {
  return true;
} else {
  return false;
}
```
```
return obj && obj.someProperty ? true : false;
```
 <!-- .element: class="fragment" -->
```
return !!obj.someProperty;
```
 <!-- .element: class="fragment" -->
___
# Double Negation

```
const obj = {
  prop: 'testing'
};
const otherObj = {};
const newObj = {
  prop: ''
}
let newestObj;
const hasProp = arg => !!arg.prop;
hasProp(obj); // true
hasProp(otherObj); // false
hasProp(newObj); // false
hasProp(newestObj);
// Uncaught TypeError: Cannot read property 'prop' of undefined
```
---

## Default Variables Values

___
## Default Variable Values
```
var vehicle;
if (!!obj.prop) {
  vehicle = obj.prop;
} else {
  vehicle = 'truck';
}
```
___
## Default Variable Values
```
var vehicle = obj.prop || 'truck';
```
___
## Default Argument Values
```
function vehicleType(type = 'truck') {
  return type;
}
const vehicleType = (type = 'truck') => type;
```
---

## Empty Object Test

```
(Object.keys(obj).length === 0)
```
---

## Converting Variable Types

```
var x = 15;
var y = x + '15';
console.log(y);
```
<!-- .element: class="fragment" -->
```
// string... '1515'
```
<!-- .element: class="fragment" -->
___

## Converting Variable Types

```
var x = '15';
var y = parseInt(x);
console.log(y);
// number 15
```
___

## Converting Variable Types

```
var x = {key:'value',key2:'value2'};
var y = Object.keys(x);
console.log(y);
// ['key','key2']
```
---

# JavaScript Tricks

## Questions?

Jeff Shamley | @jeff_shamley | https://jeffshamley.com
