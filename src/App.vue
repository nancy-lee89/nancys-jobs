<template>
  <div class="app">
    <p>{{ jobs }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from 'vue';
import Job from './types/Jobs'

export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as string | number
    // })

    // state.name = 'Sean'

    // return { ...toRefs(state) }

    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1' },
      { title: 'legal assistant', location: 'space', salary: 20, id: '2' },
      { title: 'flute player', location: 'mom house', salary: 5, id: '3' },
      { title: 'prison guard', location: 'the lost woods', salary: 10, id: '4' }
    ])

    return {jobs}
    }
  });
</script>

<style>

</style>
