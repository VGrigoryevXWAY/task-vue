<template>
      <form @submit.prevent>
          <h4>Создание поста</h4>
          <my-input 
          v-model="post.title" 
          type="text" 
          placeholder="название"
          ></my-input>
          <my-input 
          v-model="post.body"
          type="text" 
          placeholder="описание"
          ></my-input>
          <my-button
           style="margin-top: 15px"
          @click="createPost"
          >
          Создать
          </my-button>
      </form>
</template>

<script>
export default {

    data() {
        return {
            post: {
                title: '',
                body: ''
            }
        }
    },
    methods: {
        createPost() {
          this.post.id = Data.now();
          this.$emit('create', this.post)
          this.post = {
              title:'',
              bodyL:''
          }
        }
    }
}
</script>

<style scoped>
  form {
      display: flex;
      flex-direction: column;
}
</style>