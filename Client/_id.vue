<script>
export default {
  async fetch() {
    try {
      const response = await this.$axios.get(`/users/${this.$route.params.id}`);
      this.user = response.data;
    } catch (error) {
      console.error(error);
    }
  },
  data() {
    return {
      user: null,
    };
  },
};
</script>
