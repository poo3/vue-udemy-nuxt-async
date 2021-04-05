<template>
  <section>
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.id }},{{ user.name }}
      </li>
    </ul>
  </section>
</template>

<script>
import axios from "axios";
let url = "https://jsonplaceholder.typicode.com/users";
export default {
  asyncData() {
    return axios.get(url).then((response) => {
      return { users: response.data };
    });
  },
};
</script>

