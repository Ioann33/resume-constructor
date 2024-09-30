<template>
  <div class="container">
    <p>
      <AppButton
          classes="primary"
          @action="loadComments"
      >Загрузить комментарии</AppButton>
    </p>
    <div class="card" v-if="comments.length > 0">
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item" v-for="comment in comments">
          <div>
            <p><strong>{{comment.email}}</strong></p>
            <small>{{comment.body}}</small>
          </div>
        </li>
      </ul>
    </div>
    <AppLoader v-if="isLoading"></AppLoader>
  </div>
</template>

<script>
import AppButton from "@/components/Elements/AppButton.vue";
import AppLoader from "@/components/Elements/AppLoader.vue";
import axios from "axios";

export default {
  name: "AppComment",
  components: {AppLoader, AppButton},
  data() {
    return {
      isLoading: false,
      comments: []
    }
  },
  methods: {
    async loadComments(){
      this.isLoading = true
      const {data} = await axios.get('https://jsonplaceholder.typicode.com/comments?_limit=42')
      this.comments = data
      this.isLoading = false
    }
  }
}
</script>

<style scoped>

</style>