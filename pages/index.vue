<template>
  <section class="container">
    <div>
      <img src="~/assets/img-sample.jpg" alt="" />
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
  async asyncData({ $axios, error }) {
    try {
      const res = await $axios.$get(url);
      return { users: res };
    } catch (err) {
      // const statusCode = err.response ? err.response.status : 500;
      error({ statusCode: 404, message: "ページが見つかりません" });
    }
  },
};
</script>
<style></style>
