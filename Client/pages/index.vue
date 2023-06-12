export default {
    data() {
      return {
        users: [],
      };
    },
    async created() {
      try {
        const response = await this.$axios.get('/users');
        this.users = response.data;
      } catch (error) {
        console.error(error);
      }
    },
  };
  