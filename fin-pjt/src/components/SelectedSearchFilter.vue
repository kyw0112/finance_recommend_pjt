<template>
  <b-button variant="success" size="sm" class="m-1" :class="{ notSelected: !isSelected }">
    {{ searchCondition }}
  </b-button>
</template>

<script>
export default {
  name: 'SelectedSearchFilter',
  props: {
    searchCondition: String,
    isSelected: Boolean,
  },
}
</script>

<style>
  .notSelected {
    display: none;
  }
</style>