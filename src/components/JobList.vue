<template>
  <div class="job-list">
    <p>Ordered by {{ order }}</p>
    <ul>
      <li
        v-for="job in ordereJobs"
        :key="job.id"
      >
        <h2>{{ job.title }} in {{job.location}}</h2>
        <div class="salary">
          <p>{{job.salary}} rupees</p>
        </div>
        <div class="description">
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt, accusantium tempora in ea reprehenderit modi qui incidunt? Impedit iste dolore repellat ullam libero dolor aspernatur repellendus ipsum aut, tempora voluptatum.</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
import Job from '@/types/Jobs'
import OrderTerm from '@/types/OrderTerms'

export default defineComponent( {
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>
    }
  },

  setup ( props ) {
    const ordereJobs = computed( () => {
      return [ ...props.jobs ].sort( ( a: Job, b: Job ) => {
        return a[ props.order ] > b[ props.order ] ? 1 : -1
      } )
    } )

    return { ordereJobs }
  }
} )
</script>

<style scoped>
.job-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list ul {
    padding: 0;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .salary {
    display: flex;
  }
  .salary img {
    width: 30px;
  }
  .salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
</style>
