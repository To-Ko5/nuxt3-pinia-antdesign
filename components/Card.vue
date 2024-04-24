<template>
  <div>
    <a-card hoverable style="width: 240px">
      <template #cover>
        <img
          alt="example"
          src="https://os.alipayobjects.com/rmsportal/QBnOOoLaAfKPirc.png"
        />
      </template>
      <a-card-meta title="Europe Street beat">
        <template #description>{{ content }}</template>
      </a-card-meta>
    </a-card>
  </div>
</template>

<script lang="ts" setup>
const { content } = defineProps<{ content?: string }>();
</script>

<style lang="scss" scoped></style>
