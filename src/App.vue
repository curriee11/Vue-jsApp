<template>
 <ProvideInject/>
  <hr>
  <TemplateRef/>
  <hr>
  <Person/>
  <hr>
  <ClickCounter/>
  <HoverCounter/>
</template>
<script>
import ProvideInject from './components/ProvideInject.vue'
import TemplateRef from './components/TemplateRef.vue'
import Person from './components/Person.vue'
import ClickCounter from './components/ClickCounter.vue'
import HoverCounter from './components/HoverCounter.vue'

export default {
  name: 'App',
  components: {
    // DemoOne,
   ProvideInject,
   TemplateRef,
    Person,
    ClickCounter,
    HoverCounter
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
