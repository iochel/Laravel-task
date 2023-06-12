<template>
  <div>
    <h1>Users</h1>
    <ul>
      <li v-for="user in users" :key="user.id">
        <nuxt-link :to="`/user/${user.id}`">{{ user.name }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async fetch() {
    const { data } = await this.$axios.get('/users');
    this.users = data;
  },

  data() {
    return {
      users: [],
    };
  },
};
</script>
