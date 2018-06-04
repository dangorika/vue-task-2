<template>
  <div class="socials">
    <a href=""><i v-html="TwitterIcon"></i></a>
    <a href=""><i v-html="FacebookIcon"></i></a>
    <a href=""><i v-html="PinterestIcon"></i></a>
    <a href=""><i v-html="GooglePlusIcon"></i></a>
  </div>
</template>

<script>
import TwitterIcon from '~/assets/icons/twitter.svg';
import FacebookIcon from '~/assets/icons/facebook.svg';
import PinterestIcon from '~/assets/icons/pinterest.svg';
import GooglePlusIcon from '~/assets/icons/google-plus.svg';

export default {
  name: 'Social',
  data() {
    return {
      FacebookIcon,
      TwitterIcon,
      PinterestIcon,
      GooglePlusIcon
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
@import '../helpers/all'

.socials
  display: flex
  a
    text-decoration: none
    color: #fff
    width: 40px
    height: 40px
    background: #000
    border-radius: 50%
    display: block
    margin-right: 10px
    position: relative
    i
      +vcenter
      font-size: 20px

</style>
