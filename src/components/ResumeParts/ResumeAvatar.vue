<script>
export default {
  name: "ResumeAvatar",
  computed: {
    defaultSlotText() {
      // Проверяем и возвращаем текстовое содержимое слота
      return this.$slots.default && this.$slots.default()[0] && typeof this.$slots.default()[0].children === 'string'
          ? this.$slots.default()[0].children.trim()
          : '';
    }
  }
}
</script>

<template>
  <div class="avatar">
    <img :src="defaultSlotText" alt="avatar">
  </div>
</template>

<style scoped>
  .avatar {
    display: flex;
    justify-content: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>