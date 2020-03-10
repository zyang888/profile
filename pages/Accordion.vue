<template>
  <div role="tablist">
    <BlogPost v-for="post in posts" :key="post.id" :id="`accordion-` + post.id" :title="post.title" :text="post.text"/>
  </div>
</template>

<script>
import BlogPost from '../components/BlogPost.vue'

export default {
  name: 'accordionpage',
  components: {
    BlogPost
  },
  data () {
    return {
      posts: [
        { id: '1', title: 'accordion 1', text: `accordion 1` },
        { id: '2', title: 'accordion 2', text: `accordion 2` },
        { id: '3', title: 'accordion 3', text: `accordion 3` }
      ]
    }
  },
  head () {
    return {
      title: 'accordion',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'accordion', name: 'accordion', content: 'accordion description' }
      ]
    }
  },
}
</script>
