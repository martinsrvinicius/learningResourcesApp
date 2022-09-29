<template>
  <base-card>
    <base-button @click="setSelectTab('stored-resources')" :mode="storedResButton">Stored Resources</base-button>
    <base-button @click="setSelectTab('add-resource')" :mode='addResButton' >Add Resource</base-button>
  </base-card>
<!--  keeps the data stored even if moving to other tabs-->
  <keep-alive>
    <component :is='selectTab'></component>
  </keep-alive>
</template>

<script>
import StoredResources from '@/components/resources/StoredResources';
import AddResource from '@/components/resources/AddResource';

export default {
  name: 'TheResources',
  components: {
    StoredResources, AddResource
  },
  data() {
    return {
      selectTab:  'stored-resources',
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The official Vue.js documentation.',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'The official google documentation.',
          link: 'https://google.com',
        },
      ],
    };
  },
  computed: {
    storedResButton() {
      return this.selectTab === 'stored-resources' ? null : 'flat'
    },
    addResButton() {
      return this.selectTab === 'add-resource' ? null : 'flat'
    },
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      deleteResource: this.removeResource,
    };
  },
  methods: {
    setSelectTab(tab) {
      this.selectTab = tab;
    },
    addResource(title, description, url) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: url
      };
      this.storedResources.unshift(newResource);
      this.selectTab = 'stored-resources';
    },
    removeResource(resId) {
      const resIndex = this.storedResources.findIndex(res => res.id === resId);
      this.storedResources.splice(resIndex,1);
    }
  },
}
</script>

<style scoped>

</style>