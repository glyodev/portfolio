<template>
  <router-view />
</template>

<script>
export default {
  name: "AppView",
  methods: {
    async postVisita() {
      try {
        const res = await this.axios.post("/visitas");
        console.log(res.data);
      } catch (error) {
        console.log(error);
      }
    },
    async getStatus() {
      try {
        const res = await this.axios.get("/");
        console.log(res.data);
      } catch (error) {
        console.log(error);
      }
    }
  },
  created() {
    if (document.getElementsByTagName("body")[0] === "true") {
      document
        .getElementsByTagName("body")[0]
        .append(
          "<div class='preloader'><div><span>L</span><span>O</span><span>A</span><span>D</span><span>I</span><span>N</span><span>G</span></div></div>"
        );
    }
    this.postVisita();
  },
};
</script>