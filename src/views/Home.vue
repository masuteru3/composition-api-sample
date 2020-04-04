<template>
  <div>
    <p>count:{{ count }}</p>
    <button @click="increment">Count Up</button>
    <button @click="decrement">Count Down</button>
  </div>
</template>

<script>
import { ref, computed, watch, onMounted } from '@vue/composition-api'

export default {
  setup() {
    let count = ref(0)
    let double = computed(() => count.value * 2)
    // const state = reactive({
    //   count: 0,
    //   double: computed(() => state.count * 2)
    // })

    function increment() {
      count.value++
    }

    const decrement = () => count.value--
    

    watch(() => {
      if(count.value % 10 === 0) console.log('Multiple of 10')
    })

    onMounted(() => { console.log('Mounted!') })

    return {
      count,
      double,
      increment,
      decrement
    }
  }
}
</script>