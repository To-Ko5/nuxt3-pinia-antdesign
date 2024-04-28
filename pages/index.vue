<template>
  <NuxtLayout name="layout">
    <a-row :gutter="[16, 16]" :wrap="true" justify="space-between">
      <a-col v-for="(post, index) in posts" flex="12" class="cards"
        ><Card :content="post.title" />
      </a-col>
    </a-row>
  </NuxtLayout>
</template>

<script lang="ts" setup>
type posts = {
  userId: number
  id: number
  title: string
  body: string
}
const { data: posts } = await useFetch<posts[]>(
  'https://jsonplaceholder.typicode.com/posts'
)
</script>

<style lang="scss" scoped></style>
