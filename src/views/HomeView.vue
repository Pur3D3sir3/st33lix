<script setup>
import AppLoading from "@/components/UI/AppLoading.vue";
import AppFooter from "@/components/landing-page/AppFooter.vue";
import BaseCard from "@/components/UI/BaseCard.vue";
import TheNavbar from "@/components/landing-page/TheNavbar.vue";
import { Splide, SplideSlide } from "@splidejs/vue-splide";
import "@splidejs/vue-splide/css";

const newsList = [
  {
    image: "/src/assets/news/tr_festivo_9.png",
    title: "Some great news!"
  },
  {
    image: "/src/assets/news/tr_festivo_9.png",
    title: "Some Cool news!"
  }
];

const options = {
  rewind: true,
  autoplay: true,
  pagination: "slider",
  fixedHeight: "300px",
  type: "loop"
};
</script>

<template>
  <AppLoading />

  <!-- Navigation -->
  <TheNavbar />

  <div class="container">
    <div class="d-grid">
      <div class="d-none d-lg-block box">
        <BaseCard class="mt-5">
          <h5>Box Title</h5>
        </BaseCard>
      </div>

      <!-- Welcome -->
      <BaseCard class="mb-4 mt-5 align-self-start welcome">
        <h4 class="fw-bold mb-0">
          Welcome
        </h4>
      </BaseCard>

      <!-- slides -->
      <BaseCard class="mb-4 mt-5 carousel">
        <Splide :options="options">
          <SplideSlide v-for="news in newsList" :key="news.id">
            <img class="img-fluid d-block w-100 h-100" :src="news.image" />
          </SplideSlide>
        </Splide>
      </BaseCard>

      <!-- News -->
      <BaseCard class="mb-4 align-self-start news">
        <h5>Latest News</h5>
        <div class="d-flex align-items-center mt-2">
          <a class="d-flex text-decoration-none" href="#" target="_blank">
            <svg
              width="20"
              class="me-1"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M12 21.2498C17.108 21.2498 21.25 17.1088 21.25 11.9998C21.25 6.89176 17.108 2.74976 12 2.74976C6.892 2.74976 2.75 6.89176 2.75 11.9998C2.75 17.1088 6.892 21.2498 12 21.2498Z"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              ></path>
              <path
                d="M10.5576 15.4709L14.0436 11.9999L10.5576 8.52895"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              ></path>
            </svg>
            <span>View More</span>
          </a>
        </div>
      </BaseCard>
    </div>
  </div>
  <AppFooter />
</template>

<style lang="scss" scoped>
@import url(https://cdn.jsdelivr.net/npm/animate.css@4.1.1/animate.min.css);
.d-grid {
  grid-template-areas:
    "Welcome"
    "Carousel"
    "News";
  @include mq(lg) {
    grid-template-columns: 1fr 2.5fr 1fr;
    grid-template-rows: 1fr 1fr;
    gap: 10px 60px;
    grid-template-areas:
      "Box Carousel Welcome"
      "Box Carousel News";
  }
}
.box {
  grid-area: Box;
}

.welcome {
  grid-area: Welcome;
}

.carousel {
  grid-area: Carousel;
}
.news {
  grid-area: News;
  @include mq(lg) {
    margin-top: -35px;
  }
}
.characters {
  grid-area: Characters;
}
</style>
