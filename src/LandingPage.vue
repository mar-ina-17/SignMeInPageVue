<template>
  <div id="app">
    <h3 v-html="$t(`landingPage.header`)"></h3>
    <signMeInBox/>
  </div>
</template>

<script>
import signMeInBox from './components/signMeInBoxComponent.vue'

export default {
  name: 'LandingPage',
  components: {
    signMeInBox
  }
}
</script>

<style>
@import './styles/landingPageStyle.css';
</style>
