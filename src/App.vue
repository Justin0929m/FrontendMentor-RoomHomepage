
<template>
  <div>
    <NavSection class="nav-section"/>
    <HomeView class="home-section"/>
    <router-view />
  </div>
</template>

<script>
import HomeView from './views/HomeView.vue';
import NavSection from './components/NavSection.vue'

export default{
  components:{
    HomeView,
    NavSection
  }
}

</script>

<style scoped>
 
</style>
