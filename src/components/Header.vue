<template> 
  <section class="container">
    <header class="header">
    <nav class="flex flex-jc-sb flex-ai-c top-nav">
    <div class="header_logo">
      <router-link to="/">pillbank</router-link>
    </div>
    <div>
    <div @click="displayMenu" class="header-hamburger hide-for-desktop" :class="{open: open}">
        <span></span>
        <span></span>
        <span></span>
    </div>

      <div class="desk-menu hide-for-mobile">
        <router-link to="/">Home</router-link>
        <router-link :to="{name: 'About'}">About</router-link>
      </div>
    </div>
    
    <div class="mobile-menu hide-for-desktop" :class="{open: open}">
        <router-link to="/">Home</router-link>
        <router-link class="link" :to="{name: 'About'}">About</router-link>
      </div>  
  </nav>
  </header>
  </section>
</template>

<script>
export default {
  data() {
    return {
      open: false
    }

  },
  methods: {
    displayMenu(event) {
      // let hamburger = this.$refs.hamburger
      this.open = !this.open
      // console.log(hamburger);
      this.emitter.emit("display",this.open) 
     }
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