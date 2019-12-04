<template>
  <button class="el-button">
    <span v-if="$slots.default">
      <slot></slot>
    </span>    
  </button>
</template>

<script>
export default {
  name: 'ElButton',
  props: {
    type: String,
  }
}
</script>