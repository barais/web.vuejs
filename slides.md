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
- Ref, reactive, computed, watch <=>  signal, effect
- Lifecycle hooks
- Router

---

# Compatible avec TypeScript

- Demo

```bash
npm create vite@latest
cd demovue
npm i
npm run dev
```

---

# Un modèle de développement propre

1 composant = 1 fichier .vue avec trois parties (*SFC (single file component)*)


```vue
<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>
 
<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
```

---

# Partie 1 Script

Code TS permettant de 

- définir les **props** et les **emits** (équivalent input output port d'angular)
- definir les **ref** (signal en angular),  les **reactive** (signal pour types complexes), les **computed** (computed signal), les **watch** (effect en angular) => Base de la programmation reactive
- définir les  **Lifecycle Hooks**
- définir les **provide** / **inject**

⚠️: Attention dans la suite nous utiliserons que l'API composition (la nouvelle) en comparaison de l'API Options plus proche de Vue 2

---
layout: two-cols-header
---

# Props et Emits

::left::

### Props

<Transform :scale="0.95">
```ts
defineProps({
  greetingMessage: String
})
```

```html
<BlogPost title="My journey with Vue" />
```

</Transform>

You've also seen props assigned dynamically with v-bind or its : shortcut, such as in:

<!-- Dynamically assign the value of a variable -->

<Transform :scale="0.95">

```html
<BlogPost :title="post.title" />
```

</Transform>


::right::

### Emit

```ts
const emit = defineEmits<{
  increase-by: [id: number]
  update: [value: string]
}>()
```

Emit an event from code (to the parent)

```ts
emit("increase-by",23)
```

Emit an event from template (to the parent)

```html
<button @click="$emit('increase-by', 1)"> emit 1 </button>
```

Capture the event from the parent

```html
<MyButton @increase-by="(n) => count += n" />
```

---
layout: two-cols-header
---

# Ref, reactive, computed, watch

::left::

### Ref

In Composition API, the recommended way to declare reactive state is using the ref() function:

<Transform :scale="0.95">

```ts
import { ref } from 'vue'

const count = ref(0)
console.log(count) // { value: 0 }
console.log(count.value) // 0
count.value++
console.log(count.value) // 1
```

</Transform>

Close to signal in Angular

::right::

### Reactive

There is another way to declare reactive state, with the reactive() API. Unlike a ref which wraps the inner value in a special object, *reactive*() makes an object itself reactive:

```ts
import { reactive } from 'vue'

const state = reactive({ count: 0 })
```

Reactive is only for complex object

---
layout: two-cols-header
---

# Refs, reactive, computed, watch

::left::

### Without computed property


In Composition API, you can declare computed property

<Transform :scale="0.95">

```ts
const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
})
```

</Transform>

And we want to display different messages depending on if author already has some books or not:

<Transform :scale="0.95">

```html
<p>Has published books:</p>
<span>{{ author.books.length > 0 ? 'Yes' : 'No' }}</span>
```

</Transform>


::right::

### With computed property


```vue
<script setup lang="ts">
import { reactive, computed } from 'vue'

const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
})

// a computed ref
const publishedBooksMessage = computed(() => {
  return author.books.length > 0 ? 'Yes' : 'No'
})
</script>

<template>
  <p>Has published books:</p>
  <span>{{ publishedBooksMessage }}</span>
</template>
```

---

# Refs, reactive, computed, watch


### watch


Computed properties allow us to declaratively compute derived values. However, there are cases where we need to perform "side effects" in reaction to state changes - for example, mutating the DOM, or changing another piece of state based on the result of an async operation.

With Composition API, we can use the watch function to trigger a callback whenever a piece of reactive state changes:


```vue
<script setup lang="ts">
import {  ref, watch } from 'vue'
const count = ref(0)
const increment = ()=>  count.value = count.value  +2
watch(count, async (newValue, oldValue) => {  
  console.error('newValue',newValue);
  }
)
</script>
<template>
    <button type="button" @click="increment()">count is {{ count }}</button>
</template>
```

---
layout: two-cols-header
---

# Lifecycle Hooks

::left::

For example, the onMounted hook can be used to run code after the component has finished the initial rendering and created the DOM nodes:

<Transform :scale="0.95">

```vue
<script setup lang="ts">
import { onMounted } from 'vue'

onMounted(() => {
  console.log(`the component is now mounted.`)
})
</script>
```
</Transform>

::right::


- onMounted()
- onUpdated()
- onUnmounted()
- onBeforeMount()
- onBeforeUpdate()
- onBeforeUnmount()
- onErrorCaptured()
- onRenderTracked()
- onRenderTriggered()
- onActivated()
- onDeactivated()
- onServerPrefetch()

---
layout: two-cols-header
---

# provide / inject

::left::

## With props

![](/props.png)

::right::

## With provide inject



![](/provideinject.png)


---
layout: two-cols-header
---

# provide / inject

::left::

## provide



<Transform :scale="0.95">

```vue
<script setup lang="ts">
import { provide } from 'vue'

provide(/* key */ 'message', /* value */ 'hello!')
</script>
```

</Transform>

### App-level Provide​

In addition to providing data in a component, we can also provide at the app level:


<Transform :scale="0.95">

```ts
import { createApp } from 'vue'
const app = createApp({})
app.provide(/* key */ 'message', /* value */ 'hello!')
```

</Transform>


::right::

## inject

```ts
<script setup lang="ts">
import { inject } from 'vue'
const message = inject('message')
</script>
```


---
layout: two-cols-header
---

# Component registration

::left::

### Global Registration

<Transform :scale="0.95">
```ts
import MyComponent from './App.vue'
const app = createApp({})

app.component('MyComponent', MyComponent)
  .component('ComponentA', ComponentA)
  .component('ComponentB', ComponentB)
  .component('ComponentC', ComponentC)
```
</Transform>

<Transform :scale="0.95">

```html
<!-- this will work in any component inside the app -->
<ComponentA/>
<ComponentB/>
<ComponentC/>
```

</Transform>

::right::

### Local Registration

When using SFC (single file component) with *script setup*, imported components can be locally used without registration:

```vue
<script setup lang="ts">
import ComponentA from './ComponentA.vue'
</script>

<template>
  <ComponentA />
</template>
```

 Better to use local registration