<template>
  <footer class="footer">
    <div class="footer-container">
      <p>&copy; 2024 TekCorp. Hak cipta dilindungi.</p>
      <p>Aplikasi Uji Performa Vue.js Sederhana</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
.footer {
  background-color: #34495e;
  color: #ecf0f1;
  text-align: center;
  padding: 2rem 0;
  margin-top: auto;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.footer p {
  margin: 0.5rem 0;
}
</style>