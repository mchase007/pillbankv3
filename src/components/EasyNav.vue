<template>
    <section class="easy-nav" :class="{open: isOpen}">
      <div >
        <a href="#a" class="">A</a>
        <a href="#b" class="">B</a>    
        <a href="#c" class="">C</a>
        <a href="#d" class="">D</a>
        <a href="#e" class="">E</a>
        <a href="#f" class="">F</a>
        <a href="#g" class="">G</a>
        <a href="#h" class="">H</a>
        <a href="#i" class="">I</a>
        <a href="#j" class="">J</a>
        <a href="#k" class="">K</a>
        <a href="#l" class="">L</a>
        <a href="#m" class="">M</a>
        <a href="#n" class="">N</a>
        <a href="#o" class="">O</a>
        <a href="#p" class="">P</a>
        <a href="#q" class="">Q</a>
        <a href="#r" class="">R</a>
        <a href="#s" class="">S</a>
        <a href="#t" class="">T</a>
        <a href="#u" class="">U</a>
        <a href="#v" class="">V</a>
        <a href="#w" class="">W</a>
        <a href="#x" class="">X</a>
        <a href="#y" class="">Y</a>
        <a href="#z" class="">Z</a>
      </div>
    </section>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  },
  mounted() {
    this.emitter.on("display", open => {
      this.isOpen = open
    }) 
    // console.log(this.isOpen)
  },
}
</script>

<style>

</style>