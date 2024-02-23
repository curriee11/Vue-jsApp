<template>
    <div>
     <input type="text" placeholder="Name" v-model="name">

     <input type="text" placeholder="First Name" v-model="firstName">
     <input type="text" placeholder="Last Name" v-model="lastName">

      <input type="text" placeholder="Reactive First Name" v-model="fName">
     <input type="text" placeholder="Reactive Last Name" v-model="lName">
     <input type="text" placeholder="Reactive Hero Name" v-model="options.heroName">
     

    </div>
</template>

<script>
import {ref,watch,reactive, toRefs} from 'vue'
import _ from 'lodash'
    export default {
        name:'WatchComponent',
        setup(){
            const state=reactive({
                fName:'',
                lName:'',
                options:{
                    heroName:'',
                }
            })

        // watch(()=>{
        //     return {...state}
        // },function(newValue,oldValue){
        //     console.log('fname old value',oldValue.fName)
        //     console.log('fname new value',newValue.fName)
        //     console.log('lname old value',oldValue.lName)
        //     console.log('lname new value',newValue.lName)
        // })

        watch(()=>_.cloneDeep(state.options),function(newValue,oldValue){
            console.log('fname old value',oldValue)
            console.log('fname new value',newValue)
        },
        {
            deep:true
        })

         const firstName=ref('')
         const lastName=ref('Wayne')

         watch([firstName,lastName],(newValues,oldValues)=>{
             console.log('firstname old value',oldValues[0])
             console.log('firstname new value',newValues[0])
               console.log('lastname old value',oldValues[1])
             console.log('lastname new value',newValues[1])
         },{
            immediate:true
         })
         return {
                firstName,
                lastName,
                ...toRefs(state)
         }
        },
        data(){
            return {
                name:''
            }
        },
        watch:{
            name(newVal,oldVal){
                console.log('old value',oldVal)
                console.log('new value',newVal)
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>