<template>
  <section class="container">
    <section class="drug-list">
      <div class="flex flex-fd-c">
        <span>A</span>
        <div v-for="drugData in data" :key=drugData.id>
          <router-link :to="{name: 'DrugDetails', params: {id: drugData.id, drugName: drugData.drug}}" >
            <p class="drug">{{drugData.drug}}</p>
          </router-link>
        </div>
      </div>
    </section>
  </section>
  
</template>
<script>
import json from '@/assets/data/db.json';

export default {
  data() {
    return {
      data: json.data
    }
  },
  mounted() {
    // console.log(this.data);
  },

  methods: {
  },
}
</script>

<style lang="scss" scoped>
$pillGreen: hsl(181, 77%, 25%);
$pillWhite: hsl(181, 77%, 97%);

@media only screen and (min-width: 770px) {
    .class {
      font-size: 1.2rem;
    }
}
</style>