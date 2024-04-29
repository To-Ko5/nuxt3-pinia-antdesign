<template>
  <NuxtLayout name="layout">
    <a-row :gutter="[16, 16]" :wrap="true" justify="space-between">
      <a-col v-for="(post, index) in posts" flex="12" class="cards"
        ><Card :id="post.id" :user-id="post.userId" :content="post.title" />
      </a-col>
    </a-row>
  </NuxtLayout>
</template>

<script lang="ts" setup>
import { type post } from '@/types/data'
const { data: posts } = await useFetch<post[]>(
  'https://jsonplaceholder.typicode.com/posts'
)
</script>

<style lang="scss" scoped></style>
