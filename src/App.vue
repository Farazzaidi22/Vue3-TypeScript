<template>
  <div class="app">
    Hello Hyrule
    <!-- <p>{{ name }} - {{age}}</p>
    <button @click="changeName('Amil')">change name</button>
    <button @click="changeAge('35')">change age</button> -->

    <p>{{jobs[0].location}}</p>

  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import Job from './types/Jobs'

export default defineComponent( {
  name: 'App',
  components: {
  },

  setup () {
    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as number | string 
    // })

    // return{ ...toRefs(state) }

    // const name = ref('Link')
    // const age = ref<number | string>(25)

    // return { name, age }

    const jobs = ref<Job[]>( [
      { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1' },
      { title: 'quarryman', location: 'death mountain', salary: 40000, id: '2' },
      { title: 'flute player', location: 'the lost woods', salary: 35000, id: '3' },
      { title: 'fisherman', location: 'lake hylia', salary: 21000, id: '4' },
      { title: 'prison guard', location: 'gerudo valley', salary: 32000, id: '5' }
    ] )

    return { jobs }
  },

  // data(){
  //   return {
  //     name: 'Link',
  //     age: 25 as number | string
  //   }
  // },

  methods: {
    // changeName(name: string){
    //   this.name = name
    //   return name
    // },
    // changeAge(age: number | number){
    //   this.age = age
    //   return age
    // }
  }
} );
</script>

<style>
#app {

}
</style>
