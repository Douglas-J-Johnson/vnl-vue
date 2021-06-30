<template>
    <div id="search-bar">
    <input
      placeholder="Enter name and press <enter> to search"
      :value="searchTerm"
      @keyup="executeSearch"
      @input="updateSearchTerm"
    />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    searchTerm: String
  },
  methods: {
    executeSearch(event) {
      if (event.keyCode === 13) {
        this.$emit('executeSearch', event.target.value);
      }
    },
    updateSearchTerm(event) {
      this.$emit('updateSearchTerm', event.target.value);
    }
  }
}
</script>

<style scoped>
  #search-bar {
    width: 100%;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  input {
    width: 80%;
    margin: 1rem;
    padding: 0.5rem;
    text-align: center;
  }
</style>
