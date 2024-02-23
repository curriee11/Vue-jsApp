<template>
    <div>
      Composition API lifecycle hooks
    </div>
</template>

<script>
import { onBeforeMount, onBeforeUnmount, onBeforeUpdate,onUpdated, onMounted, onUnmounted } from 'vue'
    export default {
        name:'LifecycleC',
        setup(){
            onBeforeMount(()=>{
                console.log('LifecycleC onBeforeMount')
            })
            onMounted(()=>{
                console.log('LifecycleC onMounted')
            })
            onBeforeUpdate(()=>{
                console.log('LifecycleC onBeforeUpdate')
            })
            onUpdated(()=>{
                console.log('LifecycleC onUpdated')
            })
            onBeforeUnmount(()=>{
                console.log('LifecycleC onBeforeUnmount')
            })
            onUnmounted(()=>{
                console.log('LifecycleC onUnmounted')
            })
        },
    }
</script>

<style lang="scss" scoped>

</style>