<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>
    Edit <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
  <button @click="getHi">getHi</button>
  <p>{{ hi }}</p>
</template>

<script>
import { ref, defineComponent } from 'vue'
export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  setup() {
    const count = ref(0)
    const hi = ref('')

    const getHi = async () => {
      fetch('http://127.0.0.1:10071')
        .then((response) => {
          return response.text()
        })
        .then((myJson) => {
          console.log(myJson)
          hi.value = myJson
        })
    }

    return {
      count,
      hi,
      getHi,
    }
  },
})
</script>
