<script setup>
import { ref } from "vue";
let isVisible = ref(false);

function toggleNavbar() {
  isVisible.value = !isVisible.value;
}
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-transparent">
    <div class="container">
      <router-link to="/" class="navbar-brand mb-0"
        ><img
          src="@/assets/logo.gif"
          class="img-fluid d-inline"
          alt="t33lix logo"
        />
        <h4 class="d-inline-block ms-0">T33LIX</h4>
      </router-link>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarToggler"
        aria-controls="navbarToggler"
        aria-expanded="false"
        aria-label="Toggle navigation"
        @click="toggleNavbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="collapse navbar-collapse justify-content-end"
        :class="{ show: isVisible }"
        id="navbarToggler"
      >
        <ul class="navbar-nav flex-row mb-2 mb-lg-0 ms-auto">
          <li class="nav-item me-3">
            <router-link to="/register" class="btn btn-primary px-4 py-2 shadow"
              >Register</router-link
            >
          </li>
          <li class="nav-item">
            <router-link
              to="/login"
              class="px-4 py-2 btn btn-success text-white shadow"
              >Login</router-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped></style>
