<template>
    <dialog :class="{'modal-open': show}" id="modal-episode" class="modal">
        <div v-if="episode" class="modal-box">
            <form method="dialog">
                <button @click="closeModal()" class="btn btn-sm btn-circle btn-ghost absolute right-2 top-2">✕</button>
            </form>
            <h3 class="text-lg font-bold mb-4">
                {{ episode.name }}<BadgeEpisode> {{ episode.episode }}</BadgeEpisode>
            </h3>
            <div 
                class="avatar" 
                v-for="character in episode.characters"
            >
                <div class="w-12 rounded-full">
                    <img :src="getImage(character)" />
                </div>
            </div>
            <div v-if="charactersCount" class="avatar avatar-placeholder">
                <div class="bg-neutral text-neutral-content w-12">
                <span>+{{ charactersCount }}</span>
                </div>
            </div>
            <p class="py-4">
                <BadgeAirDate>{{ episode.air_date }}</BadgeAirDate>
            </p>
        </div>
        <div v-else class="modal-box">
            <div flex justify-center>
                <span class="loading loading-dots loading-xl"></span>
            </div>
        </div>
    </dialog>
</template>
<script setup>
import axios from 'axios';

const props = defineProps({
    id: String
})

const episode = ref(null)

const show = defineModel()

async function handleGetEpisodes() {
  try {
    const response = await axios.get(`https://rickandmortyapi.com/api/episode/${props.id}`)
    episode.value = response.data
  } catch (error) {
    console.error(error)
  }
}

watch(show, (newValue) => {
    if (newValue) {
        handleGetEpisodes()
    } else {
        episode.value = null
    }
})

function getImage(url) {
  const newUrl = url.replace(
    'https://rickandmortyapi.com/api/character/',
    'https://rickandmortyapi.com/api/character/avatar/',
  )
  return `${newUrl}.jpeg`
}

function closeModal() {
    show.value = false
}

</script>