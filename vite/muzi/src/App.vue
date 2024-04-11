<!-- <script setup>

  import { reactive } from 'vue'
  const web = reactive({
    show:true
  })
  const toggle= () =>{
    web.show = !web.show
  }

</script>

<template>
  <h3>{{ web.show }}</h3>
  <p v-show="web.show">木子哈哈哈——</p>
  <button @click="toggle"> 点击切换状态</button>
</template>

<style>

</style> -->
<script setup>
import { reactive } from 'vue'
import Header from './components/header.vue'
import Footer from './components/footer.vue'

  const propWeb = {
    user:10,
    url: 'rkwork'
  }
</script>

<template>
<Header/>
<Footer v-bind="propWeb" />


</template>

<style>

</style>