<template>
  <header class="header">
    <h1 class="site-title">
      <router-link to="/">
        {{ $siteData.title }}
      </router-link>
    </h1>
    <div class="nav">
      <div 
        class="nav-item" 
        :key="item.title"
        v-for="item in nav"
        >
        <a v-if="isOutboundLink(item.link)" :href="item.link" target="_blank">{{ item.title }}</a>
        <router-link v-else :to="item.link">{{ item.title }}</router-link>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  computed: {
    nav() {
      return this.$themeConfig.nav || [{title: 'home', link: '/'}]
    }
  },

  methods: {
    isOutboundLink(link) {
      return /^https?:\/\//.test(link)
    }
  }
}
</script>


<style lang="stylus" scoped>
@import "../styles/vars.styl"

.header
  margin-bottom: 30px
  display: flex

.site-title
  font-size: 1rem
  a
    text-decoration: none
    color: $red
    &:hover
      color: #333

.nav
  display: flex
  align-items: center
  margin-left: 20px

.nav-item
  margin-right: 10px
  a
    color: #aaa
    text-decoration: none
    font-weight: bold
    &:hover
      color: #333
</style>
