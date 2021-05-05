<template>
  <section class="container">
    <section class="hero flex flex-fd-c" :class="{open: isOpen}">
      
      <div>
        <p>your <span>easy-to-understand</span> drug resource</p>
      </div>

    <Search></Search>
  </section>
  </section>
</template>

<script>
import Search from '@/components/Search.vue'

export default {
  data() {
    return {
      isOpen: false,
      
    }
  },
  components: {Search},
  mounted() {
    this.emitter.on("display", open => {
      this.isOpen = open
    })
  },
  methods: {
    
  },
}
</script> 

<style lang="scss" scoped>
$pillGreen: hsl(181, 77%, 25%);
$pillWhite: hsl(181, 77%, 97%);

.container {
  background: $pillGreen;
}


</style>