<template>
  <div>
    <Html lang="ja">
      <Head>
        <Title>{{ title }}</Title>
        <Meta name="description" :content="`${description}`" />
      </Head>
    </Html>
    <div><slot /></div>
  </div>
</template>

<script setup lang="ts">
import 'ant-design-vue/dist/reset.css'
const { title, description } = defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true }
})
</script>
