<template>
  <a
    class="el-link"
    :class="[
      type ? `el-link--${type}` : '',
      {
        'is-disabled': disabled,
        'is-underline' : !disabled && underline,
      }
    ]"
    :href="disabled ? null : href"
    @click="handleClick"
  >
    <i v-if="icon" :class="icon" />
    <span v-if="$slots.default">
      <slot></slot>
    </span>
  </a>
</template>

<script>
export default {
  name: 'ElLink',

  props: {
    href: String,
    type: String,
    disabled: Boolean,
    underline: {
      type: Boolean,
      default: true
    },
    icon: String
  },

  methods: {
    handleClick (e) {
      if(!this.disabled && !this.href) {
        this.$emit('click', e);
      }
    }
  }
};
</script>
