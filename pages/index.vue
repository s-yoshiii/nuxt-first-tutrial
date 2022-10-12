<template>
  <section class="container">
    <div>
      <ul>
        <li v-for="user in users" :key="user.id">
          {{ user.id }},{{ user.name }},{{ user.company.name }}
        </li>
      </ul>
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
