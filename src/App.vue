<template>
  <div class="page-wrapper">
    <AppHeader></AppHeader>
    <PageContent></PageContent>
    <AppFooter></AppFooter>
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue'
import MainFooter from './components/MainFooter.vue'
import MainContent from './components/MainContent.vue'
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  components: {
      AppHeader : MainHeader,
      AppFooter : MainFooter,
      PageContent: MainContent,
  },
  data() {
    return {
    }
  },
  mounted() {
    AOS.init({
      disable: 'mobile',
      once: true
      });
  },
}
</script>

<style scoped>
</style>
