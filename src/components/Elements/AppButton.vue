<template>
  <div class="form-control">
    <button class="btn" :class="classes" @click="$emit('action')">
      <slot></slot>
    </button>
  </div>
</template>

<script>
export default {
  name: "AppButton",
  props: {
    classes: [Object,Array,String]
  },
  emits: ['action']
}
</script>

<style scoped lang="scss">

</style>
