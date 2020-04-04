<template>
  <div>
    <h1>samp</h1>
    {{ message }}
    {{ data }}
  </div>
</template>

<script>
import { ref, onMounted } from '@vue/composition-api'

export default {
  setup() {
    let message = ref('hello composition API!')
    let data = ref([])

    onMounted(async () => {
      data.value = await axios('https://jsonplaceholder.typicode.com/posts')
    })

    return { message, data }
  }
}
</script>

<style scoped>

</style>