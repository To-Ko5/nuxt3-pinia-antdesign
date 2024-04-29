<template>
  <NuxtLayout name="layout">
    <div>{{ post?.id }}</div>
    <div>{{ post?.title }}</div>
  </NuxtLayout>
</template>

<script lang="ts" setup>
import { type post } from '@/types/data'
const id = useRoute().params.id
const { data: post } = await useFetch<post>(
  `https://jsonplaceholder.typicode.com/posts/${id}`
)
</script>

<style lang="scss" scoped></style>
