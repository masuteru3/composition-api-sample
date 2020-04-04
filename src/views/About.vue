<template>
  <div>
    <p>count:{{ count }}</p>
    <button @click="increment">Count Up</button>
  </div>
</template>

<script>
import { ref } from '@vue/composition-api'

export default {
  setup() {
    let count = ref(0)

    function increment() {
      count.value++
    }

    return {
      count,
      increment
    }
  }
}
</script>