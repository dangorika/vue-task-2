<template>
  <div>
    <main-header></main-header>
    <transition name="fade" mode="in-out">
      <!-- <div> -->
        <nuxt />
      <!-- </div> -->
    </transition>
    <main-footer></main-footer>
  </div>
</template>

<script>
import MainHeader from '~/components/MainHeader';
import MainFooter from '~/components/MainFooter';
export default {
  name: 'MainLayout',
  components: {
    MainHeader,
    MainFooter
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass">
@import url('https://fonts.googleapis.com/css?family=Lato:400,700,900')
@import '../helpers/all'

html
  +lat-r
  font-size: 16px
  line-height: 1.4
  color: #000
  +smooth-font
svg
  width: 1em
  height: 1em
  fill: currentColor
  display: block
.l
  max-width: 950px
  margin: 0 auto
.fade-enter-active, .fade-leave-active
  transition: opacity .25s
.fade-enter-active
  transition-delay: .25s
.fade-enter, .fade-leave-to
  opacity: 0
</style>
