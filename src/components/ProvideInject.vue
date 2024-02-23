<template>
    <h3>Parent Component {{name}}</h3>
    <h3>Parent Component count {{count}}</h3>
     <h3>Parent Component Hero {{firstName}} {{lastName}}</h3>

     <button @click="incrementCount">Increment Count</button>
    <ChildA/>
</template>

<script>
import {provide,ref,reactive,toRefs} from 'vue'
import ChildA from './ChildA.vue'
    export default {
       components:{
           ChildA
       },
        name:'ProvideInjectComponent',
        setup(){
        provide('c_userName','CodeEvolution')

        const count = ref(0)
        function incrementCount(){
            count.value++
        }
        const state=reactive({
            firstName:'bruce',
            lastName:'wayne'
        })
        provide('c_count',count)
        provide('c_hero',state)
        provide('incrementCount',incrementCount)

        return {
            count,
            ...toRefs(state),
            incrementCount
        }
        },
        data(){
            return {
                name:'Vishwas'
            }
        },
        provide(){
            return{
                userName:this.name,
            }
        } 
    }
</script>

<style  scoped>

</style>