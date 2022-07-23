<script>
export default {
  setup() {
    return {
      news: {
        title: [],
        image: []
      }
    };
  }
};
</script>

<template>
  <div class="card">
    <div class="card-body">
      <slot />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
    background-color: #202022;
    border: 0 solid rgba(0, 0, 0, 0.125);
    box-shadow: 0 1rem 2rem 0 rgba(0, 0, 0, 0.25);
}
.card-title {
    margin-bottom: 0.5rem;
}
.card-subtitle {
    margin-top: -0.25rem;
}
.card-header {
    padding: 1.5rem 1.5rem;
    background-color: #202022;
    border-bottom: 0 solid rgba(0, 0, 0, 0.125);
}
.card-footer {
    padding: 1.5rem 1.5rem;
    background-color: #202022;
    border-top: 0 solid rgba(0, 0, 0, 0.125);
}

</style>
