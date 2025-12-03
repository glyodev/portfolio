<template>
  <div class="hero-section">
    <div class="container text-center">
      <h2 style="font-size: 200px">404</h2>
      <h5>Page not found</h5>
      <br />
      <button class="button" @click="$router.push('/')">
        Return home <i class="bi bi-house"></i>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "404View",
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
    document.getElementById("a-index").removeAttribute("onclick");
  },
};
</script>
