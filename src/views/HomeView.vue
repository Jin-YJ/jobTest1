<template>
  <div class="home">
    <MainPage @changePage = "changePage" v-if="pageName === 'MAIN'"/>
    <TastPage @changePage = "changePage" v-if = "pageName === 'TEST'"/>
    <ResultPage v-if = "pageName !== 'TEST' && pageName !== 'MAIN'" :jobType = type />
  </div>
</template>

<script>
// @ is an alias to /src
import MainPage from '@/components/test/MainPage.vue'
import TastPage from '@/components/test/TestPage.vue'
import ResultPage from '@/components/test/ResultPage.vue'
export default {
  name: 'HomeView',
  components: {
    MainPage,
    TastPage,
    ResultPage
  },
  data() {
    return {
      pageName : 'MAIN',
      type : '',
    }
  },
  methods : {
    changePage(name) {
      this.pageName = name;
      if(name !== 'MAIN' && name !== 'TEST') {
        this.type = name;
      }
    },

  }
}
</script>
