<template>
  <div id="app">
    <SearchBar />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import SearchBar from './components/SearchBar.vue'

@Component({
  components: {
    SearchBar
  }
})
export default class App extends Vue {}
</script>
