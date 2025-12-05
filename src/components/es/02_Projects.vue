<template>
  <div id="portfolio" class="section-box">
    <div class="section-sm bg-dark border-radius-1">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md-10 offset-md-1 col-lg-8 offset-lg-2">
            <span class="title-heading text-white-04">Portafolio</span>
            <h1 class="display-3 fw-medium">
              Tabajos <span class="text-gradient">recientes</span>
            </h1>
            <p>Mis proyectos terminados.</p>
            <div class="mt-4">
              <div
                class="swiper-portfolio-prev button-circle cursor-link"
                @mouseenter="$store.commit('expandCursor')"
                @mouseleave="$store.commit('expandCursorLeave')"
              >
                <i class="bi bi-arrow-left"></i>
                <i class="bi bi-arrow-left"></i>
              </div>
              <div
                class="swiper-portfolio-next button-circle cursor-link"
                @mouseenter="$store.commit('expandCursor')"
                @mouseleave="$store.commit('expandCursorLeave')"
              >
                <i class="bi bi-arrow-right"></i>
                <i class="bi bi-arrow-right"></i>
              </div>
            </div>
          </div>
        </div>
        <div class="swiper portfolio-slider mt-4 mt-lg-5">
          <Swiper
            class="swiper-wrapper"
            :slides-per-view="slidesPerView"
            :breakpoints="breakpoints"
            :modules="modules"
            :navigation="{
              prevEl: '.swiper-portfolio-prev',
              nextEl: '.swiper-portfolio-next',
            }"
            :pagination="{
              el: '.xp-swiper-pagination2',
              clickable: true,
            }"
          >
            <swiper-slide
              class="swiper-slide"
              v-for="(pro, id_pro) of projects.slice().reverse()"
              :key="id_pro"
              :style="pro.active ? '' : 'display:none;'"
            >
              <div class="portfolio-box">
                <div class="portfolio-img">
                  <a
                    v-if="pro.url_ins"
                    :href="pro.url_ins ? pro.url_ins : 'javascript:;'"
                    target="_blank"
                    class="badge bg-light text-black position-absolute m-3"
                    style="z-index: 9"
                    aria-disabled="true"
                  >
                    {{ pro.ins }}
                  </a>
                  <span
                    v-else
                    class="badge bg-light text-black position-absolute m-3"
                    style="z-index: 9"
                    aria-disabled="true"
                  >
                    {{ pro.ins }}
                  </span>
                  <a
                    :href="pro.url"
                    target="_blank"
                    @mouseenter="$store.commit('expandCursor')"
                    @mouseleave="$store.commit('expandCursorLeave')"
                  >
                    <img :src="require('@/' + pro.img)" alt="" />
                  </a>
                </div>
                <div class="pt-4">
                  <ul class="list-inline-dot sm-heading text-white mb-2">
                    <li v-for="(tag, id_tag) of pro.tags" :key="id_tag">
                      <a class="link-hover" href="javascript:void(0)">
                        <span :data-text="tag">{{ tag }}</span>
                      </a>
                    </li>
                  </ul>
                  <h2>
                    <a class="portfolio-caption" href="javascript:void(0)">
                      <i class="bi bi-arrow-right"></i>
                      {{ pro.nombre }}
                    </a>
                  </h2>
                </div>
              </div>
            </swiper-slide>
          </Swiper>
          <div
            class="xp-swiper-pagination2 swiper-pagination"
            @mouseenter="$store.commit('expandCursor')"
            @mouseleave="$store.commit('expandCursorLeave')"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Navigation, Pagination } from "swiper/modules";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

const proys = require("../projects.json");

export default {
  name: "projectsView",
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      projects: proys,
      slidesPerView: 2.5,
      breakpoints: {
        320: {
          slidesPerView: 1,
          spaceBetween: 5,
        },
        480: {
          slidesPerView: 1,
          spaceBetween: 10,
        },
        640: {
          slidesPerView: 1.5,
          spaceBetween: 15,
        },
        768: {
          slidesPerView: 2.0,
          spaceBetween: 20,
        },
        1024: {
          slidesPerView: 2.5,
          spaceBetween: 25,
        },
      },
    };
  },
  setup() {
    return {
      modules: [Navigation, Pagination],
    };
  },
};
</script>
