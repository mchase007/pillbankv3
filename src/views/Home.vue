<template>
    <Header></Header>
    <Hero></Hero>
    <!-- <Search></Search> -->
    <EasyNav></EasyNav>
    <DrugList></DrugList>
</template>
 
<script>
import Header from '@/components/Header.vue'
import Hero from '@/components/Hero.vue'
import EasyNav from '@/components/EasyNav.vue'
import DrugList from '@/components/DrugList.vue'
// import Search from '@/components/Search.vue'

export default {
  name: 'Home',
  components: { Header, Hero, EasyNav, DrugList },
  data() {
    return {
      // drugArr: [],
    }
  },
  methods: {

  },
  mounted() {
    
  },
}
</script>

