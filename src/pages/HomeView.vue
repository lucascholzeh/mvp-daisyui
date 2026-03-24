<script setup>
import axios from 'axios'

const episodes = ref([])

const text = ref()

async function handleGetEpisodes() {
  try {
    const response = await axios.get('https://rickandmortyapi.com/api/episode')
    episodes.value = response.data.results
  } catch (error) {
    console.error(error)
  }
}

onMounted(() => {
  handleGetEpisodes()
})
</script>

<template>
  <div class="p-4">
    <pre>
        {{ episodes }}
    </pre>
  </div>
</template>
