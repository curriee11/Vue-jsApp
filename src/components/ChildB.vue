<template>
  <h2>Child component</h2>
  <ChildC/>
</template>

<script>
import ChildC from './ChildC.vue'
    export default {
        name:'ChildB',
        components:{
            ChildC,
        }
    }
</script>

<style lang="scss" scoped>

</style>