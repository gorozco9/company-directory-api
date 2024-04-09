<script setup>
import { onMounted } from 'vue'
//const title = ref('Hello There ✋')
import MainCard from '@/components/MainCard.vue';
import MainPagination from '@/components/MainPagination.vue';
import useAPI from '@/composables/useAPI';

const { getEmployees, loading } = useAPI()

onMounted(async () => {
  await getEmployees()
})

</script>

<template>
  <p v-if="loading">LOADING...></p>
   <MainCard></MainCard>
   <MainPagination></MainPagination>
</template>
