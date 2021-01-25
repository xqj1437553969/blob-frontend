<template>
  <footer class="footer">
    <div class="container">
      <span v-text="myConfig.footer" />
    </div>
  </footer>
</template>

<script>
import myConfig from '@/assets/js/config.js';
export default {
  data() {
    return {
      myConfig: myConfig,
    };
  },
};
</script>

<style scoped>
.footer {
  font-size: 0.8rem;
  padding: 6rem 0;
}
</style>
