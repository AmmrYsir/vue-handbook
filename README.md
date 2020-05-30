<h1 align="center">Vue Handbook</h1>

<p align="center"><a href="https://vuejs.org" target="_blank" rel="noopener noreferrer"><img width="100" src="https://vuejs.org/images/logo.png" alt="Vue logo"></a></p>

### Introduction

Vue (pronounced /vjuː/, like view) is a progressive framework for building user interfaces. It is designed from the ground up to be incrementally adoptable, and can easily scale between a library and a framework depending on different use cases. It consists of an approachable core library that focuses on the view layer only, and an ecosystem of supporting libraries that helps you tackle complexity in large Single-Page Applications.

## Table of Contents
- [Introduction, Installation & Outputting Data](#introduction-installation--outputting-data)
- [Binding Data & Simple To-Do Example](#binding-data--simple-to-do-example)
- [Conditional Rendering with v-if and v-else](#conditional-rendering-with-v-if-and-v-else)
- [Computed Properties](#computed-properties)
- [Methods vs. Computed Properties](#methods-vs-computed-properties)
- [Components 101](#components-101)
- [Custom Events Passing Data from Child to Parent Component](#custom-events-passing-data-from-child-to-parent-component)
- [Making HTTP Requests with Axios with API Example](#making-http-requests-with-axios-with-api-example)
- [Introduction to Vue CLI and Vue UI Tool](#introduction-to-vue-cli-and-vue-ui-tool)
- [Class and Style Bindings](#class-and-style-bindings)
- [Vue Router](#vue-router)

## Introduction, Installation & Outputting Data
Getting started by through [Vue.js](https://vuejs.org/v2/guide/) and get the script link similar to below
```vue
<!-- development version, includes helpful console warnings -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```
Choose development version for beginner
<hr>

***1. Copy that script and paste it into head like so***

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    
    
  </body>
</html>
```
<br >

***2. Now, we're going to create Vue! inside body tag***
```html
<script>
  new Vue({
    el: '',
    data: {
    
    },
  
  })
</script>
```
<br >

***3. It will look like this!***
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app"></div>
    
    <script>
      new Vue({
        el: '#app',
        data: {

        },
      })
    </script>
  </body>
</html>
```
- el stand for Element which we will bind it into div which id is app.
- data which refer to any variable that we can define later.
<br>

***4. Outputting Data***
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app"> {{ x }} </div>
    
    <script>
      new Vue({
        el: '#app',
        data: {
            x: 'Hello World',
        },
      })
    </script>
  </body>
</html>
```
***Output:***
<br>
![Output 1](https://github.com/AmmrYsir/vue-handbook/blob/master/asset/output1.PNG)
<br>

[Back to Table of Content](#table-of-contents)

## Binding Data & Simple To-Do Example

***1. Binding Data with v-text and v-title***
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app">
      <h1 v-text="title"></h1>
      <p v-text="content"></p>
    </div>
    
    <script>
      new Vue({
        el: '#app',
        data: {
            title: 'This is Vue.js',
            content: 'Vue.js is an open-source model–view–viewmodel JavaScript framework',
        },
      })
    </script>
  </body>
</html>
```
***Output (Use v-text to bind it into any div)***
<br>
![Output 2](https://github.com/AmmrYsir/vue-handbook/blob/master/asset/output2.PNG)

***2. Binding Data as tooltip with v-bind:title***
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app">
      <h1 v-text="title" v-bind:title="tooltip"></h1>
    </div>
    
    <script>
      new Vue({
        el: '#app',
        data: {
            title: 'This is Vue.js',
            tooltip: 'Vue.js is an open-source model–view–viewmodel JavaScript framework',
        },
      })
    </script>
  </body>
</html>
```
***Output***
<br>
![Output 3](https://github.com/AmmrYsir/vue-handbook/blob/master/asset/output3.png)
<br />

[Back to Table of Content](#table-of-contents)

## Conditional Rendering with v-if and v-else

<br />

[Back to Table of Content](#table-of-contents)

## Computed Properties

<br />

[Back to Table of Content](#table-of-contents)

## Methods vs. Computed Properties

<br />

[Back to Table of Content](#table-of-contents)

## Components 101

<br />

[Back to Table of Content](#table-of-contents)

## Custom Events Passing Data from Child to Parent Component

<br />

[Back to Table of Content](#table-of-contents)

## Making HTTP Requests with Axios with API Example

<br />

[Back to Table of Content](#table-of-contents)

## Introduction to Vue CLI and Vue UI Tool

<br />

[Back to Table of Content](#table-of-contents)

## Class and Style Bindings

<br />

[Back to Table of Content](#table-of-contents)

## Vue Router

<br />

[Back to Table of Content](#table-of-contents)
 
