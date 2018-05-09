<template>
  <footer class="footer">
    <div class="box">
      <div 
        class="line" 
        v-if="$siteData.title">
        {{ $siteData.title }}
      </div>
      <div 
        class="line" 
        v-if="$siteData.description">
        {{ $siteData.description }}
      </div>
      <div 
        class="line"
        v-if="$siteData.email">
        {{ $siteData.email }}
      </div>
    </div>
    <div class="box">
      <div 
        class="line"
        v-if="$themeConfig.github">
        <a :href="`https://github.com/${$themeConfig.github}`">github.com/{{ $themeConfig.github }}</a>
      </div>
      <div 
        class="line"
        v-if="$themeConfig.twitter">
        <a :href="`https://twitter.com/${$themeConfig.twitter}`">twitter.com/{{ $themeConfig.twitter }}</a>
      </div>
    </div>
    <div class="box feed">
      <a v-if="$feedLink" :href="$feedLink.href" title="Feed">
        <img src="./rss.png" alt="Feed">
      </a>
    </div>
  </footer>
</template>

<style lang="stylus" scoped>
.footer
  border-top: 4px solid #eee
  color: #666
  margin-top: 30px
  padding-top: 30px
  font-size: 13px
  display: flex
  a
    color: #8085C1

.box
  width: 33.33333%

.feed
  text-align: right

.line
  margin-bottom: 5px
</style>
