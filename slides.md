
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
}
return false;
```
___
# Double Negation

```
return !!obj.someProperty;
```
___
# Double Negation

```
const obj = {
  prop: 'testing'
};
const otherObj = {};
function hasProp(arg) {
  return !!arg.prop;
}
hasProp(obj); // true
hasProp(otherObj); // false
```
---

# Default Variable Values

___
# Default Variable Values
```
var vehicle;
if (!!obj.prop) {
  vehicle = obj.prop;
} else {
  vehicle = 'truck';
}
```
___
# Default Variable Values
```
var vehicle = obj.prop || 'truck';
```
---

# Short Circuit Conditionals

```

```
 <!-- .element: class="fragment" -->

---

# Convert Variable Types

```
let x = 15;
x + '15';
console.log(x)
```
 <!-- .element: class="fragment" -->
 // string... '1515'
 <!-- .element: class="fragment" -->

---

# JavaScript Tricks

## Questions?

Jeff Shamley | @jeff_shamley | https://jeffshamley.com
