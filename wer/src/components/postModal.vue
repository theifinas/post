<template>
 <div class="post">
   <div class="post__id">
     id {{id}}
   </div>
   <div class="post__body">
     body {{body}}
   </div>

   <button v-on:click="closePostModal" class="post__btn">Закрыть</button>
 </div>
</template>

<script>
  import {defineComponent} from 'vue';

  export default defineComponent({
    name: 'PostModal',
    props: {
      id: Number,
      body: String
    },
    methods: {
      closePostModal() {
        this.$emit("closePostModal", false)
      }
    }
  })
</script>
