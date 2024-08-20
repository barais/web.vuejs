---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: vue.js
info: |
  ## vue.js course @Univ Rennes
  Master @istic

  Learn more at [istic](https://istic.univ-rennes.fr/)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---


<div align="center">
<svg class="logo" viewBox="0 0 128 128" width="128" height="128" ><path fill="#42b883" d="M78.8,10L64,35.4L49.2,10H0l64,110l64-110C128,10,78.8,10,78.8,10z" data-v-7193b705=""></path><path fill="#35495e" d="M78.8,10L64,35.4L49.2,10H25.6L64,76l38.4-66H78.8z" ></path></svg><!--]-->
</div>

#  Vue.js: The Progressive JavaScript Framework




<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/barais/web.vuejs" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->


---
layout: center
---

# Vue is easy

### Reactive web development concepts

---

# Templates and Data Binding

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>

<div id = "app">
{{message}}
</div>
```

```js
var app = new Vue({
  el: '#app',
  data:{
    message : 'hello Vue!'
  }
})
```

<v-click> 
<Jsfiddle id="barais/43df7hk5" width="100%" height="200" />
</v-click> 

---
layout: two-cols-header
---
# Playing with the DOM

::left::

<Transform :scale="0.95">
```html
<script src="https://cdnjs.cloudflare.com/ajax
/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>

<ul id="example-1">
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>
```


```js
var example1 = new Vue({
  el: '#example-1',
  data: {
    items: [
      { message: 'Foo' },
      { message: 'Bar' }
    ]
  }
})
```
</Transform>
::right::
<v-click> 
<Jsfiddle id="barais/9yc14k2q" width="100%" height="350" />
</v-click> 

---

# Two-Way Data Binding



```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>

<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>
```
<v-click> 
<Jsfiddle id="barais/xcw9d84y" width="100%" height="350" />
</v-click> 



---

## Two-Way Data Binding



```html
<select v-model="selected" multiple>
  <option>A</option>
  <option>B</option>
  <option>C</option>
</select>
<br>
<span>Selected: {{ selected }}</span>
```


<v-click> 
<Jsfiddle id="barais/pt2nwdkq" width="100%" height="300" />
</v-click> 



---
layout: two-cols-header
---

# Transition Effects

::left::
<Transform :scale="0.95">

```html
<script src="https://cdnjs.cloudflare.com/
ajax/libs/vue/2.4.2/vue.js"
 langage="JavaScript"></script>

<div id="demo">
  <button v-on:click="show = !show">
    Toggle
  </button>
  <transition name="fade">
    <p v-if="show">hello</p>
  </transition>
</div>
```

```js
new Vue({
  el: '#demo',
  data: {
    show: true
  }
})
```

```css
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s
}
.fade-enter, .fade-leave-to 
  opacity: 0
}
```
</Transform>

::right::

<v-click> 
<Jsfiddle id="barais/w56nxvs9" width="100%" height="300" />
</v-click> 



---
layout: center
---

# Vue can be easily integrated

### LARGE or small


---

# Components

<div align="center"><img src="/framework/img7.png" width="100%"></div>


---

# Components

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.2/vue.js" langage="JavaScript"></script>
<div id="example">
  <my-component></my-component>
</div>
```

```js
// register
Vue.component('my-component', {
  template: '<div>A custom component!</div>'
})
// create a root instance
new Vue({
  el: '#example'
})
```

---
layout: center
---

# Clean and Simple

---

# Clean and Simple
- Vue was created by Evan You after working for Google on AngularJS. You later summed up his thought process,

> I figured, what if I could just ** extract the part that I really liked** about Angular and build something **really lightweight** without all the extra concepts involved?

---

# Concepts très proches d'Angular

- composant
- binding modèle vue
- directive
- props <=> input port
- emit <=> output port
- Lifecycle hooks
- Router

---

# Compatible avec TypeScript

- Demo


