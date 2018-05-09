<template>
  <div class="posts-wrapper">
    <div class="section-title">Blog Posts</div>
    <div class="posts" v-if="posts && posts.length > 0">
      <div class="post" v-for="post in posts" :key="post.permalink">
        <span class="post-date">{{ formatDate(post.attributes.date) }}</span>
        <span class="post-date-sep">»</span>
        <router-link 
          class="post-title" 
          :to="post.permalink">
          {{ post.attributes.title }}
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
import format from 'date-fns/format'

export default {
  props: ['posts'],

  methods: {
    formatDate(v) {
      return format(v, 'DD MMM YYYY')
    }
  }
}
</script>

<style lang="stylus" scoped>
.section-title
  font-size: 15px
  font-weight: bold
  margin-bottom: 20px

.post
  font-size: 14px
  margin-bottom: 5px

.post-date
  color: #aaa
  font-size: 13px
  font-family: Monaco, "Courier New", monospace

.post-date-sep
  margin: 0 5px
</style>
