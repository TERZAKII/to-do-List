<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue'

export default defineComponent({
  name: 'Name_Age',
  components: {},
  setup() {
    // toRefs
    /*const state = reactive({
      name: 'Lake',
      age: 22 as number | string,
    })

    // We can change Value
    // state.name = 'Koke'
    // state.age = 17

    return { ...toRefs(state) }*/

    // ref
    const name = ref('Lake')
    const age = ref<number | string>(25)

    // We can change Value
    // name.value = 'Koke'
    // age.value = 17

    return { name, age }
  },

  /*data() {
    return {
      name: 'Shake',
      age: 22 as number | string,
    }
  },*/

  methods: {
    changeName(name: string) {
      this.name = name
    },
    changeAge(age: number | string) {
      this.age = age
    },
  },
})
</script>

<template>
  <div class="app">Hello, {{ name }}. Your age {{ age }}, yes?</div>
  <div>
    <button @click="changeName('Bake')">change name</button>
    <button @click="changeAge(25)">change age</button>
  </div>
</template>

<style></style>
