  
<template>
  <NavBar />
  <Messages v-if="isAuthenticated" />
  <NoAuth v-else />
</template>

<script setup>
import { authentication } from '~/helpers/useFirebase'
const { isAuthenticated } = authentication()
</script>