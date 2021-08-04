<template>
  <Header></Header>
  <Main></Main>
  <Footer></Footer>
</template>

<script>

import Main from './components/Main.vue'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Main,
    Header,
    Footer
  }
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  width: 100vw;
  background: red;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow-x: hidden;

}

</style>
