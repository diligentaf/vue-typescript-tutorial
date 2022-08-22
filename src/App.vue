<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('Zelda')">change name</button>
    <button @click="changeAge(30)">change number</button>
  </div>
</template>

<script lang='ts'>
import { defineComponent, reactive, ref, toRefs } from 'vue'
// import Job from './types/Job'

export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as number | string
    // })

    // state.name = 'shawn'
    // state.age = '26'

    // return { ...toRefs(state) }

    const name = ref('Link')
    name.value = 'yoshi'
    const age = ref<number | string>(20)
    age.value = '30'
    return { name, age }
  },
  methods: {
    changeName(name: string) {
      this.name = name
      return name
    },
    changeAge(age: string | number) {
      this.age = age
      return age
    }
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
