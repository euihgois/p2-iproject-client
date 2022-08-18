<script>
import axios from "./apis/axios";

export default {
  data() {
    return {
      file: null,
    };
  },
  methods: {
    async onSelect(event) {
      const file = event.target.files[0];
      console.log(file);
      this.file = file;
    },
    async send() {
      try {
        let formData = new FormData();
        formData.append("file", this.file);
        await axios.post("test", formData, {
          headers: {
            "Content-Type": "multipart/form-data",
          },
        });
      } catch (error) {
        console.log("erorrr");
      }
    },
  },
};
</script>

<template>
  <h1>TEST</h1>
  <form>
    <input ref="file" type="file" @change="onSelect" />
    <button @click.prevent="send">Upload</button>
  </form>
</template>
