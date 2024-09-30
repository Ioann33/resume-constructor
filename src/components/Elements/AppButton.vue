<template>
  <div class="form-control">
    <button class="btn" :class="classes" @click.prevent="$emit('action')" :disabled="disabled">
      <slot></slot>
    </button>
  </div>
</template>

<script>
export default {
  name: "AppButton",
  props: {
    classes: [Object,Array,String],
    disabled: {
      type: Boolean,
      default: false
    }
  },
  emits: ['action']
}
</script>

<style scoped lang="scss">

</style>
