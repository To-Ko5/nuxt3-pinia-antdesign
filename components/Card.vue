<template>
  <a-card hoverable>
    <nuxt-link :to="`/post/${id}`">
      <template #cover>
        <img
          alt="example"
          src="https://os.alipayobjects.com/rmsportal/QBnOOoLaAfKPirc.png"
        />
      </template>
      <a-card-meta title="Europe Street beat">
        <template #description>{{ content }}</template>
      </a-card-meta>
    </nuxt-link>
  </a-card>
</template>

<script lang="ts" setup>
const { id, userId, content } = defineProps<{
  id: number
  userId: number
  content?: string
}>()
</script>

<style lang="scss" scoped></style>
