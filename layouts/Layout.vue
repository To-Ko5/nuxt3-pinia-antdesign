<template>
  <div>
    <Html lang="ja">
      <Head>
        <Title>{{ meta.title }}</Title>
        <Meta name="description" :content="`${meta.description}`" />
      </Head>
    </Html>

    <div class="layout">
      <Header />
      <div class="layout__main">
        <div class="container">
          <slot />
        </div>
      </div>

      <Footer />
    </div>
  </div>
</template>

<script setup lang="ts">
import 'ant-design-vue/dist/reset.css'
const { title, description } = defineProps<{
  title?: string
  description?: string
}>()

const meta = {
  title: title || 'Default Title',
  description: description || 'default description'
}
</script>

<style lang="scss" scoped>
.layout {
  display: flex;
  flex-direction: column;
  min-height: 100dvh;
  &__main {
    flex-grow: 1;
  }
}

.container {
  margin: 0 auto;
  max-width: 1200px;
  padding: 16px;
}
</style>
