<template>
  <div class="mt-28">
    <Message v-for="(m, index) in messages" :key="index" :message="m" />
    <div ref="bottom" class="pb-16" />
  </div>
  <NewMessage @added="goToBottom" />
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useTimeoutFn } from '@vueuse/core'
import { database } from '~/helpers/useFirebase'
const { messages } = database()
const bottom = ref()
const { isPending, start, stop } = useTimeoutFn(() => {
  window.scrollTo({
    top: document.body.scrollHeight || document.documentElement.scrollHeight,
    behavior: 'smooth',
  })
}, 500)
onMounted(() => goToBottom())
const goToBottom = () => {
  start()
}
</script>