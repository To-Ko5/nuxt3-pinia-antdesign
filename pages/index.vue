<template>
  <NuxtLayout name="layout">
    <div class="search">
      <search-input
        :searchValue="searchValue"
        @clickSearchEvent="handleSearch"
      />
    </div>
    <a-row :gutter="[16, 16]" :wrap="true" justify="space-between">
      <a-col v-for="(post, index) in posts" flex="12" class="cards"
        ><Card :id="post.id" :user-id="post.userId" :content="post.title" />
      </a-col>
    </a-row>
  </NuxtLayout>
</template>

<script lang="ts" setup>
import { type post } from '@/types/data'
import type { RefSymbol } from '@vue/reactivity'
const { data: response } = await useFetch<post[]>(
  'https://jsonplaceholder.typicode.com/posts'
)

const searchValue = ref('')

const posts = ref(response)

const handleSearch = (data: string) => {
  console.log(data)
}
</script>

<style lang="scss" scoped>
.search {
  margin-bottom: 24px;
  max-width: 400px;
  margin-left: auto;
}
</style>
