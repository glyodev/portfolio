<template>
  <landing-page />
  <services />
  <projects />
  <archievements />
  <!-- <journal /> -->
  <contact />
</template>

<script>
import landingPage from "@/components/en/00_LandingPage.vue";
import services from "@/components/en/01_Services.vue";
import projects from "@/components/en/02_Projects.vue";
import archievements from "@/components/en/03_Achievements.vue";
// import journal from "@/components/en/04_Journal.vue";
import contact from "@/components/en/05_Contact.vue";

export default {
  name: "enHome",
  components: {
    "landing-page": landingPage,
    services: services,
    projects: projects,
    archievements: archievements,
    // journal: journal,
    contact: contact,
  },
  methods: {
    async postVisita() {
      try {
        await this.axios.post("/visitas");
      } catch (error) {
        console.log(error);
      }
    },
  },
  created() {
    document.getElementsByTagName("html")[0].setAttribute("lang", "en");
    document.getElementById("btn-lang").innerHTML = "🇺🇸";
    document.getElementById("btn-lang").setAttribute("data-text", "🇺🇸");
    document.getElementById("btn-contact").innerHTML = "CONTACT ME";
    document.getElementById("btn-contact").setAttribute("data-text", "CONTACT ME");
    document.getElementById("btn-menu").innerHTML = "MENU";
    document.getElementById("btn-menu").setAttribute("data-text", "MENU");

    document.getElementById("a-about").innerHTML = "About";
    document.getElementById("a-services").innerHTML = "Services";
    document.getElementById("a-portfolio").innerHTML = "Portfolio";
    document.getElementById("a-awards").innerHTML = "Awards";
    document.getElementById("a-testimonial").innerHTML = "Expercience";
    // document.getElementById("a-blog").innerHTML = "Blog";
    document.getElementById("a-contact").innerHTML = "Contact";
    document.getElementById("copyright").innerHTML = "All Rights Reserved";

    document.getElementsByTagName("body")[0].classList.remove("loaded");
    document.getElementById("a-index").removeAttribute("onclick")

    this.postVisita();
  },
};
</script>