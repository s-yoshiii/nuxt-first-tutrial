<template>
  <section class="container">
    <div>
      {{ users[0].id }}
      {{ users[0].name }}
    </div>
  </section>
</template>

<script>
const axios = require("axios");
let url = "https://jsonplaceholder.typicode.com/users";
export default {
  async asyncData({ $axios }) {
    const res = await $axios.$get(url);
    return { users: res };
  },
};
</script>
<style></style>
