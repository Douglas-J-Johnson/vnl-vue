<template>
    <div id="search-bar">
    <input placeholder="Enter name and press <enter> to search" @keyup="executeSearch"/>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
  },
  methods: {
    executeSearch: function (event) {
      if (event.keyCode === 13) {
        this.$emit('executeSearch', event.target.value);
      }
    }
  }
}
</script>

<style scoped>
  #search-bar {
    width: 100%;
    padding: 0.5rem;
    display: flex;
    justify-content: center;
  }

  input {
    width: 80%;
    padding: 0.5rem;
  }
</style>
