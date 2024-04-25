<template>
  <div>
    <Html lang="ja">
      <Head>
        <Title>{{ meta.title }}</Title>
        <Meta name="description" :content="`${meta.description}`" />
      </Head>
    </Html>
    <a-extract-style>
      <Header />
      <slot />
    </a-extract-style>
  </div>
</template>

<script setup lang="ts">
import 'ant-design-vue/dist/reset.css'
const { title, description } = defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true }
})

const meta = {
  title: title || 'Default Title',
  description: description || 'default description'
}
</script>
