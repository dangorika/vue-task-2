<template>
  <nav class="main-nav">
    <router-link to="/"><i class="main-nav__icon" v-html="HomeIcon"></i></router-link>
    <router-link to="/">News</router-link>
    <router-link to="/">Tutorials</router-link>
    <router-link to="/">Inspiration</router-link>
    <router-link to="/">Wordpress</router-link>
  </nav>
</template>

<script>
// import HomeIcon from 'vue-material-design-icons/home.vue';
import HomeIcon from '~/assets/icons/home.svg';

export default {
  data() {
    return {
      HomeIcon
    }
  },
  name: 'MainNav',
  components: {
    // HomeIcon
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
@import '../helpers/all'

.main-nav
  &__icon
    font-size: 16px
    color: #fff
  a
    opacity: .8
    color: #fff
    text-decoration: none
    text-transform: uppercase
    font-size: 16px
    margin-left: 28px
    display: inline-block
    vertical-align: middle
    +trans
    &:hover, &.is-active
      opacity: 1
</style>
