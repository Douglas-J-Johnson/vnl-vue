<template>
  <div id="app">
    <SearchBar @executeSearch="executeSearch"></SearchBar>
    <ActorsList :actors="actors"></ActorsList>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar.vue';
import ActorsList from './components/ActorsList';

export default {
  name: 'App',
  components: {
    SearchBar,
    ActorsList
  },
  data() {
    return {
      actors: [],
    };
  },
  methods: {
    executeSearch(searchTerm) {
      axios.get('http://api.tvmaze.com/search/people', {
          params: {
            q: searchTerm
          }
        })
        .then(response => {
          this.actors = response.data;
          this.actors.forEach(actor => console.log(JSON.parse(JSON.stringify(actor))));
        });
    }
  }
}
</script>

<style>
</style>
