<template>
  <div class="home">
    <div class="l">
      <div class="home__search">
        <search-input @search="doSearch" />
      </div>
    </div>
    <div class="home__tabs">
      <tabs>
        <!-- <search-input /> -->
        <tab
          name="Business"
          :selected="true"
        >
          <post
            v-for="post in filteredList"
            v-bind:key="post.id"
            v-bind:title="post.title"
            v-bind:content="post.brief"
            v-bind:date="post.date"
            v-bind:img="post.img"
          ></post>

        </tab>
        <tab
          name="Mobile"
        >
          <post
            v-for="post in filteredList"
            v-bind:key="post.id"
            v-bind:title="post.title"
            v-bind:content="post.brief"
            v-bind:date="post.date"
            v-bind:img="post.img"
          ></post>

        </tab>
        <tab
          name="Social media"
        >
          <post
            v-for="post in filteredList"
            v-bind:key="post.id"
            v-bind:title="post.title"
            v-bind:content="post.brief"
            v-bind:date="post.date"
            v-bind:img="post.img"
          ></post>

        </tab>
        <tab
          name="Technology"
        >
          <post
            v-for="post in filteredList"
            v-bind:key="post.id"
            v-bind:title="post.title"
            v-bind:content="post.brief"
            v-bind:date="post.date"
            v-bind:img="post.img"
          ></post>
        </tab>
      </tabs>
    </div>
  </div>
</template>

<script>
import Tabs from '~/components/Tabs';
import Tab from '~/components/Tab';
import Post from '~/components/Post';
import SearchInput from '~/components/SearchInput';

export default {
  name: 'Home',
  data() {
    return {
      tabs: [],
      posts: [],
      search: ''
    }
  },
  transition() {
    return 'slide'
  },
  components: {
    Tabs,
    Tab,
    Post,
    SearchInput
  },
  mounted() {
    let _this = this;

    let xhr = new XMLHttpRequest();
    xhr.onreadystatechange = function() {
      if (this.readyState == 4 && this.status == 200) {
        let data = JSON.parse(this.responseText);
        _this.posts = data;
      }
    };
    xhr.open('GET', 'https://api.myjson.com/bins/z6hli', true);
    xhr.send();
  },
  methods: {
    doSearch(data) {
      this.search = data;
    }
  },
  computed: {
    filteredList() {
      return this.posts.filter(post => {
        return post.title.toLowerCase().includes(this.search.toLowerCase())
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
@import '../helpers/all'

.slide-enter-active
  transition: opacity .5s ease-in-out, transform .5s ease-in-out
.slide-leave-active
  transition: opacity .5s ease-in-out, transform .5s ease-in-out

.slide-enter, .slide-leave
  transform: translateY(10vh)
  opacity: 0
.slide-enter-to, .slide-leave-to
  transform: translateY(0)
  opacity: 1
.l
  position: relative
  margin: 0 auto
.input
  input
    appearance: none
    border: 1px solid transparent
    border-radius: 0
    font-size: 14px
    color: #000
    padding: 10px
    background: transparent
    min-width: 250px
    +trans
    +placeholder
      +trans
    &:focus
      border: 1px solid rgba(0, 0, 0, .8)
      +placeholder
        color: #000

.home
  &__search
    position: absolute
    top: 12px
    left: 0
    z-index: 2
</style>
