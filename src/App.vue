<template>
  <div class="app">
    Hello Hyrule
    <p>{{ name }} - {{age}}</p>
    <button @click="changeName('Amil')">change name</button>
    <button @click="changeAge('35')">change age</button>

  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {
  },

  data(){
    return {
      name: 'Link',
      age: 25 as number | string
    }
  },

  methods: {
    changeName(name: string){
      this.name = name
      return name
    },
    changeAge(age: number | number){
      this.age = age
      return age
    }
  }
});
</script>

<style>
#app {

}
</style>
