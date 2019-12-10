<template>
  <a
    class="el-link"
    :class="[
      type ? `el-link--${type}` : '',
      {
        'is-disabled': disabled,
      }
    ]"
    :href="disabled ? null : href"
  >
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: 'ElLink',

  props: {
    href: String,
    type: String,
    disabled: Boolean,
  },
};
</script>
