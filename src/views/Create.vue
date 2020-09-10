<template>
  <div class="row">
    <div class="col s6 offset-s3">
      <h1>Create Task</h1>
      <form>
        <div class="input-field">
          <input
            v-model="title"
            id="title"
            type="text"
            class="validate"
            required
          />
          <label for="title">Title</label>
          <span class="helper-text" data-error="Title is required"></span>
        </div>

        <div class="chips mb-4" ref="chips"></div>

        <div class="input-field">
          <textarea
            v-model="description"
            id="description"
            class="materialize-textarea"
          ></textarea>
          <label for="description">Description</label>
          <span class="character-counter" style="float: right; font-size: 12px;"
            >{{ description.length }}/2048</span
          >
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "create",
  data: () => ({
    description: "",
    title: "",
  }),
  mounted() {
    M.Chips.init(this.$refs.chips, {
      placeholder: "Add tags :)",
    });
  },
};
</script>
