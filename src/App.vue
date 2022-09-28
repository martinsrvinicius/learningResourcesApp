<template>
  <ul>
    <learning-resource v-for="res in storedResources" :key='res.id'
    :title="res.title"
    :description="res.description"
    :link="res.link"/>
  </ul>
</template>

<script>
import LearningResource from '@/components/resources/LearningResource';

export default {
  components: {
    LearningResource
  },
  name: 'App',
  data() {
    return {
      storedResources: [
        { id: 'official-guide',
          title: 'Official Guide',
          description: 'The official documentation',
          link: 'https://vuejs.org'
        },
        { id: 'google',
          title: 'Official Google Guide',
          description: 'The official documentation',
          link: 'https://google.com'
        }
      ]
    }
  }
};
</script>

<style scoped>

</style>