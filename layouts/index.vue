<template>
  <div class="container">
    <Header />
    <Posts :posts="page.posts" />
    <Footer />
  </div>
</template>

<script>
import Header from '../components/Header'
import Posts from '../components/Posts'
import Footer from '../components/Footer'

export default {
  components: {
    Header,
    Posts,
    Footer
  },

  head() {
    return {
      title: this.$siteData.title,
      meta: [
        {
          name: 'description',
          content: this.$siteData.description
        }
      ],
      link: [
        this.$feedLink
      ].filter(Boolean)
    }
  },

  props: ['page']
}
</script>
