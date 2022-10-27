<template>
  <ForumList v-for="category in categories"
             :forums="getForumsByCategories(category)"
             :title="category.name"
             :category-id="category.id"
             :key="category.id"/>
</template>

<script>
import ForumList from '@/components/ForumList'
import sourceData from '@/data.json'

export default {
  name: 'CategoryList',
  components: { ForumList },
  props: {
    categories: {
      required: true,
      type: Array
    }
  },
  methods: {
    getForumsByCategories (category) {
      return sourceData.forums.filter(forum => forum.categoryId === category.id)
    }
  }
}
</script>

<style scoped>

</style>
