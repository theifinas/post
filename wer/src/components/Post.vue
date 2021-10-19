<template>
  <q-list dark bordered separator style="max-width: 318px">
    <q-item clickable v-ripple>
      <q-item-section v-on:click="changeIsClicked">{{post.title}}</q-item-section>
    </q-item>
  </q-list>
  <PostModal v-if="isClicked" :id="post.id" :body="post.body" @closePostModal="closePostModal"/>
</template>

<script>
  import {defineComponent} from 'vue'
  import PostModal from "../components/PostModal";

  export default defineComponent({
    name: 'Post',
    props: {
      post: {
        type: Object
      }
    },
    components: {
      PostModal
    },
    data() {
      return {
        isClicked: false
      }
    },
    methods: {
      changeIsClicked() {
        this.isClicked = true
        console.log(this.isClicked)
      },
      closePostModal(value) {
        this.isClicked = value
      }
    },
  })

</script>
