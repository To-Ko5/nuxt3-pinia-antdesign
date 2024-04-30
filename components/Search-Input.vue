<template>
  <div>
    <a-input-search
      v-model:value="search"
      placeholder="input search text"
      enter-button="Search"
      size="large"
      @search="onSearch"
    />
  </div>
</template>

<script lang="ts" setup>
const { searchValue } = defineProps<{
  searchValue: string
}>()

const emit = defineEmits(['clickSearchEvent'])

const search = ref(searchValue)

const onSearch = () => {
  emit('clickSearchEvent', search.value)
}
</script>

<style lang="scss" scoped></style>
