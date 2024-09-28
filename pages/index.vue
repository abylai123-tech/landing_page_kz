<template>
  <div class="homepage">
    <Header />
    <LaurusFooter />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import LaurusFooter from '@/components/LaurusFooter.vue';

export default {
  components: {
    Header,
    LaurusFooter
  }
};
</script>

<style scoped lang="scss">
.homepage {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  min-height: 100vh;
  width: 100%;
  margin: 0; 
  padding: 0; 
  overflow: hidden;
  background-color: #003d33;
}
</style>
