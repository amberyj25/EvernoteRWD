<template>
  <div id="sidebarRWDStyle" class="browser_all" :class="{sidebarRWDStyle:isSidebarRwdStatus}">
    <Header @sidebarRwdFixed="sidebarRwdFixed"></Header>
    <Main></Main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Main from '@/components/Main.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  },
  data() {
    return {
      isSidebarRwdStatus: false,
    }
  },
  methods: {
    sidebarRwdFixed(payload) {
      this.isSidebarRwdStatus = payload;
    }
  }
}
</script>
<style>
/* 部分 css reset */
a {
  text-decoration: none;
}
body {
  margin:0;
}
h1, h2, h3, h4, h5 ,h6 {
  margin: 0;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
.browser_all {
  min-width: 250px;
}
/* container */
.container {
  width: 60%;
  padding: 0 20px;
  margin: auto;
}
@media (max-width:1200px) {
  .sidebarRWDStyle {
    position: fixed;
  }
  .container {
    width: 100%;
    padding: 0;
  }
}

</style>