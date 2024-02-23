<template>
    <div>
      <button @click="incrementCount">Clicked {{count}} times</button>
    </div>
</template>

<script>
// import CounterMixin from '../mixins/counter.js'
import useCounter from '../composables/useCounter.js'
    export default {
        name:'ClickCounter',
          setup(){
        const {count,incrementCount}=useCounter(100,10)
        return {count,incrementCount}
        },
        // mixins:[CounterMixin],
    }
</script>

<style lang="scss" scoped>

</style>