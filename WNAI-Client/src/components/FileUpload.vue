<template>
  <form novalidate @submit.prevent="onSubmit">
    <file-upload v-model="form.file"></file-upload>
  </form>
</template>

<script>
import fileUpload from "fileUpload";
export default {
  components: { fileUpload },
  data: () => ({ form: { file: null } }),
  methods: {
    onSubmit() {
      console.log(this.form);
      // post the form to the server
    },
  },
};
</script>
