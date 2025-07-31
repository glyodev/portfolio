<template>
  <div id="about" class="hero-section">
    <div class="container text-center">
      <div class="row">
        <div class="col-12">
          <h1 class="hero-heading display-1 fw-bold mb-0 stroke-tex" id="name-typing"></h1>
          <span class="cursor-type" id="cursor-type"></span>
        </div>
      </div>
    </div>
  </div>

  <div class="container">
    <div class="row g-4 g-md-5">
      <div class="col-12 col-lg-4 order-lg-2 text-center">
        <!-- Hero Avatar -->
        <div class="hero-avatar">
          <img src="@/assets/gary.jpg" alt="" />
        </div>
      </div>
      <div class="col-12 col-lg-4 order-lg-1">
        <div class="row g-4 g-lg-5">
          <div class="col-12 col-md-4 col-lg-12">
            <h6 class="sm-heading">Biography</h6>
            <p>
              Self-taught student, teacher instructor and developer.
              I am a responsible, I like to learn, especially share my knowledge.
            </p>
          </div>
          <div class="col-6 col-md-4 col-lg-12">
            <h6 class="sm-heading">Skills</h6>
            <ul class="list-inline-dot">
              <li>Web Development</li>
              <li>FullStack</li>
              <li>Mobile App</li>
              <li>SysAdmin</li>
              <li>DBA</li>
              <li>Networking</li>
              <li>Ethical Hacking</li>
              <li>Security</li>
              <li>DevOps</li>
            </ul>
          </div>
          <div class="col-6 col-md-4 col-lg-12">
            <h6 class="sm-heading">Portfolio</h6>
            <ul class="list-inline">
              <li>
                <a class="button-circle button-circle-sm" href="https://github.com/garycdev" target="_blank"
                  @mouseenter="$store.commit('expandCursor')" @mouseleave="$store.commit('expandCursorLeave')">
                  <i class="bi bi-github"></i>
                  <i class="bi bi-github"></i>
                </a>
              </li>
              <!-- <li>
                <a
                  class="button-circle button-circle-sm"
                  href="https://gitlab.com/gcoddev"
                  target="_blank"
                  @mouseenter="$store.commit('expandCursor')"
                  @mouseleave="$store.commit('expandCursorLeave')"
                >
                  <i class="bi bi-gitlab"></i>
                  <i class="bi bi-gitlab"></i>
                </a>
              </li> -->
              <li>
                <a class="button-circle button-circle-sm expand" href="https://www.linkedin.com/in/garycdev"
                  target="_blank" @mouseenter="$store.commit('expandCursor')"
                  @mouseleave="$store.commit('expandCursorLeave')">
                  <i class="bi bi-linkedin"></i>
                  <i class="bi bi-linkedin"></i>
                </a>
              </li>
              <li>
                <a class="button-circle button-circle-sm expand"
                  href="https://garycdev.my.canva.site/en"
                  target="_blank" @mouseenter="$store.commit('expandCursor')"
                  @mouseleave="$store.commit('expandCursorLeave')">
                  <i class="bi bi-file-person"></i>
                  <i class="bi bi-file-person"></i>
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div class="col-12 col-md-12 col-lg-4 order-lg-3 text-lg-end">
        <div class="row g-4 g-lg-5">
          <div class="col-6 col-lg-12">
            <h6 class="sm-heading">Projects Done</h6>
            <h1 class="fw-light display-4 mb-0 line-height-110">
              {{ projects.length }}+
            </h1>
          </div>
          <div class="col-6 col-lg-12">
            <h6 class="sm-heading">Years of Experience</h6>
            <h1 class="fw-light display-4 mb-0 line-height-110">
              {{ experience }}+
            </h1>
          </div>
          <div class="col-12 col-md-12 col-lg-12">
            <h6 class="sm-heading">Social Hub</h6>
            <ul class="list-inline">
              <!-- <li>
                <a
                  class="button-circle button-circle-sm"
                  href="mailto:contact@garycdev.com?subject=Mensaje"
                  @mouseenter="$store.commit('expandCursor')"
                  @mouseleave="$store.commit('expandCursorLeave')"
                >
                  <i class="bi bi-envelope-fill"></i>
                  <i class="bi bi-envelope-fill"></i>
                </a>
              </li> -->
              <!-- <li>
                <a
                  class="button-circle button-circle-sm"
                  href="https://api.whatsapp.com/send/?phone=59167032056&text=Hi+Gary"
                  target="_blank"
                  @mouseenter="$store.commit('expandCursor')"
                  @mouseleave="$store.commit('expandCursorLeave')"
                >
                  <i class="bi bi-whatsapp"></i>
                  <i class="bi bi-whatsapp"></i>
                </a>
              </li> -->
              <li>
                <a class="button-circle button-circle-sm" href="https://www.youtube.com/@garycdev" target="_blank"
                  @mouseenter="$store.commit('expandCursor')" @mouseleave="$store.commit('expandCursorLeave')">
                  <i class="bi bi-youtube"></i>
                  <i class="bi bi-youtube"></i>
                </a>
              </li>
              <li>
                <a class="button-circle button-circle-sm" href="https://www.facebook.com/garycdev/" target="_blank"
                  @mouseenter="$store.commit('expandCursor')" @mouseleave="$store.commit('expandCursorLeave')">
                  <i class="bi bi-facebook"></i>
                  <i class="bi bi-facebook"></i>
                </a>
              </li>
              <li>
                <a class="button-circle button-circle-sm" href="https://www.instagram.com/garycdev" target="_blank"
                  @mouseenter="$store.commit('expandCursor')" @mouseleave="$store.commit('expandCursorLeave')">
                  <i class="bi bi-instagram"></i>
                  <i class="bi bi-instagram"></i>
                </a>
              </li>
              <li>
                <a class="button-circle button-circle-sm" href="https://x.com/garycdev" target="_blank"
                  @mouseenter="$store.commit('expandCursor')" @mouseleave="$store.commit('expandCursorLeave')">
                  <i class="bi bi-twitter-x"></i>
                  <i class="bi bi-twitter-x"></i>
                </a>
              </li>
              <li>
                <a class="button-circle button-circle-sm" href="https://www.tiktok.com/@garycdev" target="_blank"
                  @mouseenter="$store.commit('expandCursor')" @mouseleave="$store.commit('expandCursorLeave')">
                  <i class="bi bi-tiktok"></i>
                  <i class="bi bi-tiktok"></i>
                </a>
              </li>
              <!-- <li>
                <a
                  class="button-circle button-circle-sm"
                  href="https://www.udemy.com/user/gary-apaza-mamani/"
                  target="_blank"
                  @mouseenter="$store.commit('expandCursor')"
                  @mouseleave="$store.commit('expandCursorLeave')"
                >
                  <i class="bi bi-udemy"></i>
                  <i class="bi bi-udemy"></i>
                </a>
              </li> -->
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
#name-typing {
  /* font-size: 24px; */
  /* font-family: Arial, sans-serif; */
  white-space: pre;
  display: inline;
}

.cursor-type {
  display: inline-block;
  width: 2px;
  height: 5rem;
  background-color: white;
  animation: blink 1s step-end infinite;
  margin-left: 5px;
}

@keyframes blink {

  from,
  to {
    background-color: transparent;
  }

  50% {
    background-color: white;
  }
}
</style>

<script>
const proys = require("../projects.json");

export default {
  name: "LandingPage",
  data() {
    return {
      name: "Hi!\nI'm Gary",
      index: 0,
      projects: proys,
    };
  },
  computed: {
    experience() {
      const startDate = new Date(2022, 0);
      const actualDate = new Date();

      let years = actualDate.getFullYear() - startDate.getFullYear();
      const months = actualDate.getMonth() - startDate.getMonth();

      // Si el mes actual es anterior al mes de inicio, resta 1 año
      if (months < 0 || (months === 0 && actualDate.getDate() < startDate.getDate())) {
        years--;
      }

      return years;
    },
  },
  methods: {
    typing() {
      if (this.index < this.name.length) {
        document.getElementById("name-typing").innerHTML += this.name.charAt(
          this.index
        );
        this.index++;
        setTimeout(this.typing, 150);
      } else {
        // document.getElementById("cursor-type").style.display = "none";
        document
          .getElementById("a-lang")
          .setAttribute("onclick", "redirectTo('/')");
        // document
        //   .getElementById("a-index")
        //   .setAttribute("onclick", "redirectTo('/')");
      }
    },
  },
  created() {
    document.getElementsByTagName("body")[0].classList.remove("loaded");
    document.getElementById("a-index").removeAttribute("onclick");
  },
  mounted() {
    // document.getElementById("cursor-type").style.display = "inline-block";
    document.getElementById("name-typing").innerHTML = "";
    this.index = 0;
    this.typing();
    document.getElementsByTagName("body")[0].classList.add("loaded");
  },
};
</script>