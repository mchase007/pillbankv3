<template>
<div class="search-container">
    <div class="container-2">
    <VueFuse 
    :list="drugArr" 
    :fuse-opts="options"
    :keys="opts.keys" 
    :search="drugSearch"
    :map-results="false"
    placeholder="Aspirin"
    class="search-bar"
    @fuse-results="searchResultsTask"
    :defaultAll="false" />

    <!-- <input class="button" type="button" value="x"> -->
    <div class="clear-button">CLEAR</div>

    </div>
    <div v-for="(drugg, i) in searchResults"
        :key="i"
        class="drug-items">
        <router-link :to="{name: 'DrugDetails', params: {id: drugg.item.id, drugName: drugg.item.drug}}" >
            <div class="drug-item">{{drugg.item.drug}}</div>
        </router-link>

        
    </div>
    
</div>
  
</template>
  
<script>
import VueFuse from 'vue-fuse'
import json from '@/assets/data/db.json';

export default {
    components: {VueFuse},
    data() {
        return {
            drugArr: json.data,
            advanced: false,
            includeScore: false,
            searchResults: [],
            drugSearch: '',
            searchMatch: false,
            // drugArr: [],
            // filteredArr: []
            opts: {
            keys: ["drug"]
            }
        }
    },
    computed: {
    options () {
      return {
        keys: [
          {
            name: 'drug',
            // weight: 2,
          },
        //   'description'0,
        ],
        // includeScore: this.includeScore,
      }
    },
  },

    methods: {
        testSearch() {
            console.log(this.drugSearch.toLowerCase())
        },
        reset() {
            this.drugSearch = ''
        },
        searchResultsTask(r) {
            this.searchResults = r
        },
        display() {
            console.log(this.searchResults);
        }

    },
    // mounted() {
    //     fetch('http://localhost:3000/data')
    //         .then(res => res.json())
    //         .then(data => this.drugArr = data)
    //         .catch(err => console.log(err.message))
            
    //     // console.log(this.searchResults.length);

    //     // this.drugArr.forEach(drug => {
    //     //     this.filteredArr.push(drug.drug)
    //     // });
    //     // console.log(this.filteredArr);
    // },
}
</script>

<style lang='scss'>

</style>