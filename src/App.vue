<template>
  <div class="app">
    <p>{{name}} - {{age}}</p>
    <button @click="changeName('Zelda')">Change name</button>
    <button @click="changeAge(21)">Change age</button>
    <button @click="changeAge('32')">Change age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as string | number
    // });
    // state.name = 999 cannot change type

    const name = ref('Yoshi');
    const age = ref<number | string>(25);

    age.value = 30;

    return {
      // ...toRefs(state),
      name, age
    }
  },
  // data() {
  //   return {
  //     name: 'Link',
  //     age: 25 as number | string,
  //   };
  // },
  // methods: {
  //   changeName(name: string) {
  //     this.name = name;
  //     return name;
  //   },
  //   changeAge(age: string | number) {
  //     this.age = age;
  //     return age;
  //   },
  // }
});
</script>

<style>
</style>
