<template>
  <div class="col-full">
    <form @submit.prevent="save" action="">

      <div class="form-group">
        <label for="thread_content">Content:</label>
        <textarea
          v-model="text"
          id="thread_content"
          class="form-input"
          name="content"
          rows="8"
          cols="140"
        ></textarea>
      </div>

      <div class="btn-group">
        <button class="btn btn-ghost">Cancel</button>
        <button class="btn btn-blue" type="submit" name="Publish">
          Publish
        </button>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      text: "",
    };
  },
  methods: {
    save() {
      const post = { //creates de post
        text: this.text,
      };
      this.$emit('save', {post}) //access under eventData.post

      this.text = "";
    },
  },
};
</script>
