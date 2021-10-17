<template>
  <div class="post">
    <div v-for="(post, ind) in posts" :key="ind">
      <p class="post__userId">{{post.userId}}</p>
      <p class="post__title">{{post.title}}</p>
    </div>
  </div>
</template>

<script>
  import {defineComponent} from 'vue'
  import axios from 'axios'
  export default defineComponent ( {
    name: "Post",
    data() {
      return {
        posts: null
      }
    },
    methods:{
      getPost(){
        axios({
          method: 'get',
          url: 'https://jsonplaceholder.typicode.com/posts'
        }).then((result) => {
          this.posts = result.data
        })
          .catch((error) => {
            console.log(error)
          })
      }
    },
    mounted() {
      this.getPost()
    }
  })
</script>

<style scoped>

</style>
