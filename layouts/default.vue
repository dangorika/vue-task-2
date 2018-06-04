<template>
  <div>
    <main-header></main-header>
    <transition name="fade">
      <div>
        <nuxt />
      </div>
    </transition>
    <main-footer></main-footer>
  </div>
</template>

<script>
import 'vue-material-design-icons/styles.css'

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
// .material-design-icon > .material-design-icon__svg
//   position: static !important
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


<!-- <template>
  <div>
    <div>header</div>
    <nuxt/>
    <div>footer</div>
  </div>
</template>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
 -->
