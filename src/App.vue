<script setup>
import { ref, onMounted } from 'vue';
import InformationCard from './components/InformationCard.vue';
import UserProfileCard from './components/UserProfileCard.vue';

const userData = ref([]);
const selectedTimeFrame = ref("daily")

const fetchUserData = async () => {
  try {
    const response = await fetch("/db/data.json");
    const jsonData = await response.json()
    userData.value = jsonData
  } catch (error) {
    console.error("Error loading data: ", error)
  }
}

onMounted(() => fetchUserData())

const getClickedValue = (s) => {
  selectedTimeFrame.value = s
}

</script>

<template>
  <UserProfileCard @handleClick="getClickedValue" />
  <InformationCard v-for="{title, timeframes},index in userData" :card-title="title"
    :current-time-value="timeframes[selectedTimeFrame].current"
    :previous-time-value="timeframes[selectedTimeFrame].previous" :key="index" />

</template>
