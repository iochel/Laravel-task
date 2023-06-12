<script>
export default {
  data() {
    return {
      user: null,
    };
  },
  async mounted() {
    const userId = this.$route.params.id;
    try {
      const response = await this.$fetch(`/users/${userId}`);
      this.user = response.data;
    } catch (error) {
      console.error(error);
    }
  },
};
</script>
