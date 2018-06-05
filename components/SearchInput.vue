<template>
  <div class="input">
    <input
      v-model="search"
      @input="searchItem"
      placeholder="Search">
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
  data() {
    return {
      search: ''
    }
  },
  methods: {
    searchItem: function() {
      this.$emit('search', this.search);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
@import '../helpers/all'

.input
  input
    appearance: none
    border: none
    border-radius: 0
    font-size: 14px
    color: #000
    padding: 10px
    background: transparent
    min-width: 250px
    +placeholder
      +trans
    &:focus
      +placeholder
        color: #000
</style>
