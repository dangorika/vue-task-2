<template>
  <router-link to="/post-1" class="btn-more">
    <i v-html="ArrowRightIcon"></i>
    <span class="btn-more__text">read more</span>
  </router-link>
</template>

<script>
import ArrowRightIcon from '~/assets/icons/more.svg';
export default {
  name: 'BtnMore',
  data() {
    return {
      ArrowRightIcon
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
@import '../helpers/all'

.btn-more
  text-decoration: none
  +trans
  &:hover
    opacity: .7
  &__text
    margin-left: 14px
  i
    font-size: 22px
    display: inline-block
    vertical-align: middle
  span
    display: inline-block
    vertical-align: middle
    color: #000
    +lat-b
    text-transform: capitalize
    // &:not(.btn-more__text)
    //   border: 1px solid #000
    //   border-radius: 50%
    //   width: 20px
    //   height: 20px
    //   font-size: 12px
    //   position: relative
</style>
