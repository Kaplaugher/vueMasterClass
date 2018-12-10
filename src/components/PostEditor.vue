<template>
  <form @submit.prevent="save">
    <div class="form-group">
      <textarea
        v-model="text"
        name=""
        id=""
        cols="30"
        rows="10"
        class="form-input"
      ></textarea>
    </div>
    <div class="form-actions">
      <button class="btn-blue">Submit Post</button>
    </div>
  </form>
</template>

<script>
export default {
  props: {
    threadId: {
      required: true
    }
  },
  data() {
    return {
      text: ''
    };
  },
  methods: {
    save() {
      const postId = 'greatPost' + Math.random();
      const post = {
        text: this.text,

        threadId: this.threadId
      };
      // this.$set(this.$store.state.posts, postId, post);
      // this.$set(this.thread.posts, postId, postId);
      // this.$set(this.$store.state.users[post.userId].posts, postId, postId);
      this.text = '';

      this.$emit('save', { post });
      this.$store.dispatch('createPost', post);
    }
  }
};
</script>

<style scoped>
</style>