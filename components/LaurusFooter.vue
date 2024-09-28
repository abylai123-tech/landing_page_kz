<template>
  <footer class="footer">
    <div class="footer-content">
      <p>LAURUS INVEST LLP</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'LaurusFooter'
};
</script>

<style scoped lang="scss">
@import url("https://fonts.googleapis.com/css?family=Roboto");

.footer {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #003d33;
  padding: 20px 0;
  width: 100%;
  text-align: center;
  font-family: 'Inter', sans-serif;

  .footer-content {
    color: #ffffff;
    font-size: 14px;
  }
}

@media (max-width: 768px) {
  .footer {
    padding: 10px 0; 
  }

  .footer-content {
    position: relative;
    font-size: 12px; 
    bottom: 100px;
  }
}
</style>
