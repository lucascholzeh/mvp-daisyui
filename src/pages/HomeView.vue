<script setup>
import CardBase from '@/components/CardBase.vue'
import ModalEpisodes from '@/components/ModalEpisodes.vue'
import axios from 'axios'

const episodes = ref([])

const page = ref(1)
const totalPages = ref(0)
const modal = ref(false)
const episodeSelected = ref('')

async function handleGetEpisodes() {
  try {
    const response = await axios.get('https://rickandmortyapi.com/api/episode', {
      params: {
        page: page.value,
      },
    })
    episodes.value = response.data.results
    totalPages.value = response.data.info.pages
  } catch (error) {
    console.error(error)
  }
}

function setPagination(newPage) {
  page.value = newPage
  handleGetEpisodes()
}

function openModal(episodeId) {
  episodeSelected.value = episodeId.toString()
  modal.value = true
}

onMounted(() => {
  handleGetEpisodes()
})

</script>

<template>
  <div class="p-4">
    <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-6">
      <CardBase
        v-for="episode in episodes" :key="episode.id"
        :name="episode.name"
        :episode="episode.episode"
        :air_date="episode.air_date"
        :characters="episode.characters"
        @clickEpisode="openModal(episode.id)"
      />
    </div>
    <div class="flex justify-center py-4">
      <div class="join">
        <button
          class="join-item btn btn-lg md:btn-md"
          v-for="(i, index) in totalPages" :key="index"
          :class="{ 'btn-active': (index + 1) === page }"
          @click="setPagination(index + 1)"
        >
          {{ index + 1 }}
        </button>
      </div>
    </div>

    <ModalEpisodes 
      v-model="modal"
      :id="episodeSelected"
    />

  </div>
</template>
