<template>
  <h1> {{ category.name }}</h1>
  <ForumList :title="category.name"
             :forums="getForumsForCategory(category)"/>
</template>

<script>
import sourceData from '@/data.json'
import ForumList from '@/components/ForumList'

export default {
  name: 'Category',
  components: { ForumList },
  props: {
    id: {
      required: true,
      type: String
    }
  },

  data () {
    return {
      categories: sourceData.categories
    }
  },

  computed: {
    category () {
      return sourceData.categories.find(category => category.id === this.id)
    }
  },
  methods: {
    getForumsForCategory (category) {
      return sourceData.forums.filter(forum => forum.categoryId === category.id)
    }
  }
}
</script>

<style scoped>

</style>
