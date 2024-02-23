<template>
   <h2>Child Component</h2>
   <h3>Child Component C username - {{userName}}</h3>
   <h3>Child Component C Composition username - {{childUserName}}</h3>

   <h3>Child Component C count - {{childCount}}</h3>
   <h3>Child Component C hero - {{firstName}} {{lastName}}</h3>

   <button @click="incrementCount">increment Count from child</button>
</template>

<script>
import {inject,toRefs} from 'vue'
    export default {
        name:'ChildC',
        setup(){
            const childUserName=inject('c_userName','Default Username')
            const childCount=inject('c_count',0)
            const childHero=inject('c_hero',{})
            const incrementCount=inject('incrementCount')
            return {
                childUserName,
                childCount,
                ...toRefs(childHero),
                incrementCount
            }
        },
        inject:['userName']
    }
</script>

<style lang="scss" scoped>

</style>