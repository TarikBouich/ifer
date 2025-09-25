<!-- <template>
  <div class="loader">
    <div class="relative uppercase text-8xl md:text-6xl font-bold tracking-widest">Loading</div>
  </div>
</template> -->

<template>
  <transition name="fade">
    <div v-if="show" class="fixed inset-0 bg-white flex flex-col justify-center items-center z-50">
      <!-- Bird Animation / Logo Scaling -->
      <div
        :class="['mb-4 transition-all duration-[3000ms]']"
        :style="{ width: logoWidth + 'vw' }"
      >
        <img src="@/assets/logoifer.jpeg" alt="Houbara" class="w-full h-auto" />
      </div>
      <!-- Text -->
      <h1 class="text-4xl font-bold mt-4">IFER</h1>
    </div>
  </transition>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const show = ref(true)
const logoWidth = ref(20) // initial width in vw

onMounted(() => {
  // Animate logo width to 50% of screen
  setTimeout(() => {
    logoWidth.value = 50
  }, 50)

  // Hide preloader after 3 seconds
  setTimeout(() => {
    show.value = false
    const videos = document.querySelectorAll('video')
    videos.forEach(video => {
      video.play().catch(err => console.log('Video play error:', err))
    })
  }, 7000)
})
</script>

<style>
/* Simple fade animation */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

