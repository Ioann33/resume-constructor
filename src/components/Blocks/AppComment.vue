<template>
  <div class="container">
    <p>
      <AppButton
          classes="primary"
      >Загрузить комментарии</AppButton>
    </p>
    <div class="card">
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item">
          <div>
            <p><strong>test@microsoft.com</strong></p>
            <small>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi, reiciendis.</small>
          </div>
        </li>
      </ul>
    </div>
    <AppLoader></AppLoader>
  </div>
</template>

<script>
import AppButton from "@/components/Elements/AppButton.vue";
import AppLoader from "@/components/Elements/AppLoader.vue";

export default {
  name: "AppComment",
  components: {AppLoader, AppButton}
}
</script>

<style scoped>

</style>