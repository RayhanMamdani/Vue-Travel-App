

<template>
  <TheNavigation/>
      <br>
      
  <div class="container">
    <router-view v-slot="{Component}">
    <transition name="fade" mode="out-in">
      <component :is="Component" :key="$route.path"></component>
    </transition>
  </router-view>

  </div>
</template>

<script>
import TheNavigation from './components/TheNavigation.vue'
export default{
  components: {TheNavigation}
}
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>