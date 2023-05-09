<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by salary</button>
        <button @click="handleClick('location')">order by location</button>
      </div>
    </header>
    <!-- JobList is the component, jobs is the prop that was defined in JobList.vue as 
    a required PropType.'jobs' comes from the Job interface from the Job.ts file
    the : are placed before each prop  -->
    <JobList :jobs="jobs" :order="order"/>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from 'vue';
import JobList from './components/JobList.vue';
import Job from './types/Job';
import OrderTerm from './types/OrderTerm'

export default defineComponent({
  name: 'App',
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1' },
      { title: 'legal assistant', location: 'space', salary: 20, id: '2' },
      { title: 'flute player', location: 'mom house', salary: 5, id: '3' },
      { title: 'prison guard', location: 'the lost woods', salary: 10, id: '4' }
    ])
    const order = ref<OrderTerm>('title')

    const handleClick = (term: OrderTerm) => {
      order.value = term
    }

    return { jobs, handleClick, order }
    }
  });
</script>

<style>
  header {
    text-align: center;
  }
  header .order {
    margin-top: 20px;
  }
  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }

</style>
