<template>
  <Header>
  </Header>
  <section class="container">
    <section class="about flex flex-fd-c flex-jc-c" :class="{open: isOpen}">
    <h1 class="title">Hi,</h1>
    <p class="">
      Pillbank is a simplified resource with a primary focus on:
    </p>
    <ul class="focus-list">
      <li>You (the non-clinician reader)</li>
      <li>What medications do</li>
      <li>How medications work</li>
    </ul>
    <p class="">
      to improve health literacy, medication adherence and health outcomes.
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
      font-weight: 400;
    }

    .focus-list {
      margin-top: -8px;
      margin-bottom: -8px;
    }

    .focus-list li{
      font-size: 1.18rem;
      // list-style: none;
    }
  }

  @media only screen and (min-width: 770px) {
    .about p {
      font-size: 1.35rem;
      line-height: 30px;
    }

    .focus-list li{
      font-size: 1.23rem;
      // list-style: none;
    }
}

</style>