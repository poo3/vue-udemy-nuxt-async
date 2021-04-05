<template>
  <section>
    <div>{{ users[0].id }},{{ users[0].name }}</div>
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

