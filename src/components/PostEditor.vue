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
        publishedAt: Math.floor(Date.now() / 1000),
        threadId: this.threadId,
        userId: 'jUjmgCurRRdzayqbRMO7aTG9X1G2',
        '.key': postId
      };
      // this.$set(this.$store.state.posts, postId, post);
      // this.$set(this.thread.posts, postId, postId);
      // this.$set(this.$store.state.users[post.userId].posts, postId, postId);
      this.text = '';

      this.$emit('save', { post });
    }
  }
};
</script>

<style scoped>
</style>