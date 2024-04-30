<template>
  <NuxtLayout name="layout">
    <div>
      <h2>{{ error?.statusCode }}</h2>
      <a-button size="large" @click="handleError">Clear errors</a-button>
    </div>
  </NuxtLayout>
</template>

<script lang="ts" setup>
import type { NuxtError } from '#app'

const { error } = defineProps({
  error: Object as () => NuxtError
})

const handleError = () => clearError({ redirect: '/' })
</script>

<style lang="scss" scoped></style>
