<template>
  <div id="contact" class="section pb-0">
    <div class="container">
      <div class="row g-4 g-xl-5">
        <div class="col-12 col-xl-4">
          <span class="title-heading text-white-04">Contact</span>
          <h1 class="display-3 fw-medium mb-0">
            Let's <span class="text-gradient">Talk</span>
          </h1>
        </div>
        <div class="col-12 col-xl-8">
          <div class="row g-4 g-lg-5">
            <div class="col-12 col-md-6">
              <h6 class="sm-heading">Email:</h6>
              <a href="mailto:contact@garycdev.com?subject=Mensaje" target="_blank" class="button button-dot"
                @mouseenter="$store.commit('expandCursor')" @mouseleave="$store.commit('expandCursorLeave')">
                <h5 class="mb-0 text-lowercase">
                  <i class="bi bi-envelope"></i>
                  &nbsp;contact@garycdev.com
                </h5>
              </a>
            </div>
            <div class="col-12 col-md-6">
              <h6 class="sm-heading">Whatsapp:</h6>
              <a href="https://api.whatsapp.com/send/?phone=59167032056&text=Hi+Gary" target="_blank"
                class="button button-dot" @mouseenter="$store.commit('expandCursor')"
                @mouseleave="$store.commit('expandCursorLeave')">
                <h5 class="mb-0">
                  <i class="bi bi-whatsapp"></i>
                  &nbsp;+591 67032056
                </h5>
              </a>
            </div>
          </div>
          <div class="contact-form mt-4 mt-lg-5 text-xl-end">
            <form method="post" id="contactform" @submit.prevent="submitMail">
              <div class="row gx-3 gy-0">
                <div class="col-12 col-md-5">
                  <input type="text" id="name" name="name" v-model="name" placeholder="Name" required />
                </div>
                <!-- <div class="col-12 col-md-6">
                  <input type="email" id="email" name="email" placeholder="E-Mail" required />
                </div> -->
                <div class="col-12 col-md-7">
                  <input type="text" id="subject" name="subject" v-model="subject" placeholder="Subjetc" required />
                </div>
              </div>
              <textarea name="message" id="message" v-model="message" placeholder="Message" required></textarea>
              <button class="button button-dot" type="submit" @mouseenter="$store.commit('expandCursor')"
                @mouseleave="$store.commit('expandCursorLeave')">
                <span data-text="Send message">Send message</span>
              </button>
            </form>
            <div class="submit-result">
              <span id="success">Thank you! Your Message has been sent.</span>
              <span id="error">Something went wrong, Please try again!</span>
            </div>
          </div>
        </div>
      </div>
      <div id="map1" class="gmap gmap-md border-radius-1 mt-5"></div>
    </div>
  </div>
</template>

<script>
import { Loader } from "@googlemaps/js-api-loader";

export default {
  name: "contactView",
  data() {
    return {
      map: null,
      subject: '',
      name: '',
      message: ''
    };
  },
  methods: {
    loadGoogleMaps() {
      const loader = new Loader({
        apiKey: process.env.VUE_APP_API_MAPS_KEY,
        version: "weekly",
      });

      loader
        .load()
        .then((google) => {
          this.initMap(google);
        })
        .catch((e) => {
          console.error("Error loading Google Maps API", e);
        });
    },
    initMap(google) {
      this.map = new google.maps.Map(document.getElementById("map1"), {
        center: { lat: -16.480784, lng: -68.283376 },
        zoom: 16,
      });
    },
    submitMail() {
      const subject = this.subject
      const name = this.name
      const message = this.message

      const correo = `mailto:contact@garycdev.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent('De: ' + name + '\n\n' + message)}`;
      // console.log(correo);

      window.location.href = correo;
    }
  },
  mounted() {
    this.loadGoogleMaps();
  },
};
</script>