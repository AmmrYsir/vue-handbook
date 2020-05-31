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

***3. Simple To-Do Example with v-for***
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app">
      <ul>
          <li v-for="list in todolist"> {{ list }} </li>
      </ul>
    </div>
    
    <script>
      new Vue({
        el: '#app',
        data: {
            todolist: [
                'A',
                'B',
                'C',
                'D',
                'E',
                'F',
            ]
        },
      })
    </script>
  </body>
</html>
```
***Output***
<br>
![Output 4](https://github.com/AmmrYsir/vue-handbook/blob/master/asset/output4.PNG)
<br>

[Back to Table of Content](#table-of-contents)

## Conditional Rendering with v-if and v-else

***1. Create Simple Todo List***
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app">
        <ul>
            <li v-for="list in Todo">
                {{ list.content }}
                <strong v-text="list.checked"></strong>
            </li>
        </ul>
    </div>
    
    <script>
      new Vue({
        el: '#app',
        data: {
            Todo: [
                {content: 'Do Homework', checked: true },
                {content: 'Buy weekly groceries', checked: false },
                {content: 'Play with everyone', checked: true },
                {content: 'Finish part-time project', checked: false },
            ]
        },
      })
    </script>
  </body>
</html>
```

***2. Add v-if to li tag***
```html
  <div id="app">
      <ul>
          <li v-for="list in Todo" v-if="list.checked">
              {{ list.content }}
              <strong v-text="list.checked"></strong>
          </li>
      </ul>
  </div>
```
***Output:***
<br>
![Output 5](https://github.com/AmmrYsir/vue-handbook/blob/master/asset/output5.PNG)
<br>
***You also can do vice-versa by changing v-if="!list.checked"***

***3. Use v-else statement***
```html
  <div id="app">
      <ul>
          <li v-for="list in Todo" v-if="list.checked">
              {{ list.content }}
              <strong v-text="list.checked"></strong>
          </li>
          <li v-else>
              This list is not checked!
          </li>
      </ul>
  </div>
```
***Output:***
<br>
![Output 6](https://github.com/AmmrYsir/vue-handbook/blob/master/asset/output6.PNG)

***4. Dynamic button to check and uncheck the list***
```html
  <div id="app">
      <ul>
          <li v-for="list in Todo" v-if="list.checked">
              {{ list.content }}
              <strong v-text="list.checked"></strong>
              <button type="submit" @click="list.checked = !list.checked">Uncheck</button>
          </li>
          <li v-else>
              This list is not checked!
              <button type="submit" @click="list.checked = !list.checked">Uncheck</button>
          </li>
      </ul>
  </div>
```
***Output:***
<br>
![Output 7](https://github.com/AmmrYsir/vue-handbook/blob/master/asset/output7.PNG)

***Simple Todo Example 2***
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app">
        <table>
            <thead>
                <th>Content</th>
                <th>Checked</th>
                <th>Action</th>
            </thead>
            <tbody>
                <tr v-for="list in Todo" v-if="list.checked">
                    <td v-text="list.content"></td>
                    <td><strong v-text="list.checked"></strong></td>
                    <td><button type="submit" @click="list.checked = !list.checked">Uncheck</button></td>
                </tr>
                <tr v-else>
                    <td v-text="list.content"></td>
                    <td><strong v-text="list.checked"></strong></td>
                    <td><button type="submit" @click="list.checked = !list.checked">Check</button></td>
                </tr>
            </tbody>
        </table>
    </div>
    
    <script>
      new Vue({
        el: '#app',
        data: {
            Todo: [
                {content: 'Do Homework', checked: false },
                {content: 'Buy weekly groceries', checked: false },
                {content: 'Play with everyone', checked: true },
                {content: 'Finish part-time project', checked: false },
            ]
        },
      })
    </script>
  </body>
</html>
```

<br>

[Back to Table of Content](#table-of-contents)

## Computed Properties

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vue Js Newbies</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app>
      <h3>Salary: {{ salary }} </h3>
	    <h3>KWSP rate (RM): {{ kwsp }}</h3>
	    <h3>Money in hand: {{ salary - kwsp }} </h3>
    </div>
    <script>
      new Vue({
        el: '#app',
        data: {
          salary: 1500,
        },
        computed: {
          kwsp: function() {
            return this.salary * 0.11
          }
        },
      })
    </script>
  </body>
</html>
```

<br>

[Back to Table of Content](#table-of-contents)

## Methods vs. Computed Properties


<br>

[Back to Table of Content](#table-of-contents)

## Components 101

<br>

[Back to Table of Content](#table-of-contents)

## Custom Events Passing Data from Child to Parent Component

<br>

[Back to Table of Content](#table-of-contents)

## Making HTTP Requests with Axios with API Example

<br>

[Back to Table of Content](#table-of-contents)

## Introduction to Vue CLI and Vue UI Tool

<br>

[Back to Table of Content](#table-of-contents)

## Class and Style Bindings

<br>

[Back to Table of Content](#table-of-contents)

## Vue Router

<br>

[Back to Table of Content](#table-of-contents)
 
