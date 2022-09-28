<template>
  <li>
    linha teste
    <div>
      <header>
        <h3>{{ title }}</h3>
        <button>Delete</button>
      </header>
    </div>
    <p>{{ description }}</p>
    <nav>
      <a :href='link'>View Resource</a>
    </nav>
  </li>
</template>

<script>
export default {
  name: 'LearningResource',
  props: ['title', 'description', 'link'],
};
</script>

<style scoped>

</style>