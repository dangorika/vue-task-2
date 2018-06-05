<template>
  <div class="tabs">
    <div class="tabs__nav">
      <div class="l">
        <ul>
          <li
            v-for="tab in tabs"
            v-bind:key="tab.id">
            <a
              :href="tab.href"
              :class="{ 'is-active': tab.isActive }"
              @click="selectTab(tab)"
            >{{ tab.name }}</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="tabs__content">
      <div class="l">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Tabs',
  created() {
    this.tabs = this.$children;
  },
  methods: {
    selectTab(selectedTab) {
      this.tabs.forEach(tab => {
        tab.isActive = (tab.name == selectedTab.name);
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
.tabs
  &__nav
    background: #f8f8f8
    border-bottom: #d4d4d4
    .l
      position: relative
    ul
      width: percentage(508/950)
      margin-left: auto
      display: flex
    li
      margin-left: 28px
    a
      text-decoration: none
      color: #000
      display: block
      padding: 20px 0
      &.is-active
        border-bottom: 1px solid #000
  &__content
    padding: 70px 0
  &__search
    position: absolute
    top: 50%
    left: 0
    transform: translateY(-50%)
</style>
