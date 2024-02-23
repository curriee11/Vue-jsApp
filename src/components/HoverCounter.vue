<template>
    <div>
      <h2 @mouseover="incrementCount">Hover {{count}} times</h2>
    </div>
</template>

<script>
// import CounterMixin from '../mixins/counter.js'
import useCounter from '../composables/useCounter.js'
    export default {
        name:'HoverCounter',
        setup(){
        const {count,incrementCount}=useCounter()
        return {count,incrementCount}
        },
        // mixins:[CounterMixin],

    }
</script>

<style lang="scss" scoped>

</style>