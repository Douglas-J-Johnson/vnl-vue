<template>
  <div id="app">
    <div v-if="!hasActorSelected()" id="search">
      <SearchBar
        :searchTerm="searchTerm"
        @executeSearch="executeSearch"
        @updateSearchTerm="updateSearchTerm">
      </SearchBar>
      <ActorsList
        :actors="actors"
        @selectActor="selectActor"
      ></ActorsList>
    </div>
    <div v-if="hasActorSelected()" id="actor-network">
      <ActorNetwork
        :selectedActor="selectedActor"
        @resetSearch="resetSearch"
      ></ActorNetwork>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar.vue';
import ActorsList from './components/ActorsList';
import ActorNetwork from './components/ActorNetwork';

export default {
  name: 'App',
  components: {
    SearchBar,
    ActorsList,
    ActorNetwork
  },
  data() {
    return {
      searchTerm: "",
      actors: [],
      selectedActor: {}
    };
  },
  methods: {
    executeSearch(searchTerm) {
      this.searchTerm = searchTerm;

      axios.get('http://api.tvmaze.com/search/people', {
          params: {
            q: searchTerm
          }
        })
        .then(response => {
          this.actors = response.data;
          this.actors.forEach(actor => console.log(JSON.parse(JSON.stringify(actor))));
        });
    },
    selectActor(selectedActor) {
      this.selectedActor = selectedActor;
    },
    resetSearch() {
      console.log('Last Search Term', this.searchTerm);
      this.selectedActor = {};
    },
    hasActorSelected() {
      return Object.keys(this.selectedActor).length > 0;
    },
    updateSearch(searchTerm) {
      this.searchTerm =searchTerm;
    }
  }
}
</script>

<style>
</style>
