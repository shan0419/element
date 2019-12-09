<template>
  <button
    :autofocus="autofocus"
    @click="e => $emit('click', e)"
    :type="nativeType"
    class="el-button"
    :class="[
      type ? `el-button--${type}` : '',
      size ? `el-button--${size}` : '',
      {
        'is-plain': plain,
        'is-round': round,
        'is-circle': circle,
        'is-disabled': disabled,
        'is-loading': loading,
      },
    ]"
  >
    <i v-if="icon && !loading" :class="icon" />
    <i v-if="loading" class="el-icon-loading" />
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
    plain: Boolean,
    round: Boolean,
    circle: Boolean,
    icon: String,
    disabled: Boolean,
    loading: Boolean,
    size: String,
    autofocus: Boolean,
    nativeType: {
      type: String,
      default: 'button'
    }
  }
};
</script>
