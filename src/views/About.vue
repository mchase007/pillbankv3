<template>
  <Header>
  </Header>
  <section class="container">
    <section class="about flex flex-fd-c flex-jc-c" :class="{open: isOpen}">
    <h1 class="title">Hi,</h1>
    <p class="">
      Pillbank is for our curious reader who may not be medically savvy.
      <br><br>
      Caring clinical practitioners have decided to compile, exactly like this copy, a simple and short yet concise explantion of how your drugs work.
      <br><br>
      We hope this helps you appreciate and follow the counsel given on taking your drugs right for better treatment outcomes.
    </p>
    <p class="">
      Thanks.
    </p>
  </section>
  </section>
  
  
</template>

<script>
import Header from '@/components/Header.vue'
export default {
  name: 'About',
  components: { Header },
  data() {
    return {
      isOpen: false
    }
  },
  mounted() {
    this.emitter.on("display", open => {
      this.isOpen = open
    })
  },
}
</script>

<style lang="scss" scoped>

  $pillGreen: hsl(181, 77%, 25%);
  $pillWhite: hsl(181, 77%, 97%);

  .container {
    background: $pillGreen;
  }

  .about {
    background-color: hsl(181, 77%, 25%);
    height: 100vh;
    width: 95%;
    max-width: 1200px;
    margin: 0 auto;
      
    p {
        font-size: 1.25rem;
        line-height: 30px;
        max-width: 500px;
    }
    &.open {
        padding-top: 70px;
    }
    h1 {
      font-size: 2rem;
    }
  }

  @media only screen and (min-width: 770px) {
    .about p {
      font-size: 1.35rem;
      line-height: 30px;
    }
}

</style>
