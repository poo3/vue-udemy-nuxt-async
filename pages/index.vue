<template>
  <section>
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.id }},{{ user.name }},{{ user.company.name }}
      </li>
    </ul>
  </section>
</template>

<script>
import axios from "axios";
let url = "https://jsonplaceholder.typicode.com/usersxxx";
export default {
  asyncData(params, error) {
    return axios
      .get(url)
      .then((response) => {
        return { users: response.data };
      })
      .catch((e) => {
        error({ users: e.response.status, message: e.message });
      });
  },
};
</script>

