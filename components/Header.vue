<template>
  <a-page-header
    style="border: 1px solid rgb(235, 237, 240)"
    title="Title"
    sub-title="This is a subtitle"
    class="header"
  >
    <a-button type="primary" @click="showDrawer">Open</a-button>
    <a-drawer
      title="Basic Drawer"
      placement="right"
      :closable="false"
      v-model:visible="visible"
      :after-visible-change="afterVisibleChange"
    >
      <p>Some contents...</p>
      <p>Some contents...</p>
      <p>Some contents...</p>
    </a-drawer>
  </a-page-header>
</template>

<script lang="ts" setup>
const visible = ref<boolean>(false)

const afterVisibleChange = (bool: boolean) => {
  console.log('visible', bool)
}

const showDrawer = () => {
  visible.value = true
}
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}
</style>
