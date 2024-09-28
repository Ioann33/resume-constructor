<script>
export default {
  name: "ResumeAvatar",
  props: {
    url: String
  }
}
</script>

<template>
  <div class="avatar">
    <img :src="url" alt="avatar">
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