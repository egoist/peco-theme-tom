<template>
  <div class="container">
    <Header />
    <div class="page">
      <h1 class="page-title">{{ page.attributes.title }}</h1>
      <div class="page-meta">
        <span class="page-date">
          {{ formatDate(page.attributes.date) }}
        </span>
      </div>
      <div class="page-body">
        <slot name="body"></slot>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import format from 'date-fns/format'
import Header from '../components/Header'
import Footer from '../components/Footer'

export default {
  components: {
    Header,
    Footer
  },

  head() {
    let desc = this.page.attributes.subtitle || this.page.excerpt || ''
    // Strip HTML
    desc = desc.replace(/<\/?([a-z][a-z0-9]*)\b[^>]*>?/gi, '')

    return {
      title: `${this.page.attributes.title} - ${this.$siteData.title}`,
      meta: [
        {
          name: 'description',
          content: desc
        }
      ]
    }
  },

  props: ['page'],

  methods: {
    formatDate(v) {
      return format(v, 'DD MMM YYYY')
    }
  }
}
</script>

<style src="../styles/markdown.css"></style>
<style src="../styles/highlight.css"></style>

<style lang="stylus" scoped>
.page-title
  font-size: 16px

.page-meta
  color: #aaa

.page-body
  font-size: 15px
  line-height: 1.5
  margin-top: 20px
</style>
