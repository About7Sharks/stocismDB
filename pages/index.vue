<template>
  <section class="container">
    <div>
      <h1 class="title">
        Stocism
      </h1>

      <div class="parallax">
      </div>
      <br><br>
      <div class="quoteBox">
        <p>"{{$store.state.quotes[index].content}}"</p>
        <span>
          <h5>{{$store.state.quotes[index].reference}}</h5>
          <h5>{{$store.state.quotes[index].author}}</h5>
        </span>
      </div>
      <div class="links">
        <br>
        <button @click="moreWisdom" class="button--grey">More Wisdom</button>
        <br><br><br>
      </div>
<!-- <div class="about">
      <h2>This project was made using Nuxt.js</h2>
      <br>
      <p>Anytime you click the button a new quote is grabbed from the vuex store :) Souce code is <a href="">on my
          github. </a>The project was inpsired by <a href="https://stoic.thehomepage.io/">another stoic site</a> and one of my favorite books Meditations by
        Marcus Aurelius</p>
</div> -->
    </div>
  </section>
</template>

<script>
  import Logo from '~/components/Logo.vue'
  export default {
    data() {
      return {
        quotes: null,
        index: 1,
      }
    },
    components: {
      Logo
    },
    methods: {
      moreWisdom: function (index) {
        let items = this.$store.state.quotes.length
        const min = 0
        this.index = Math.floor(Math.random() * (items - min )) + min
       console.log(items)


      }
    }
  }

</script>

<style>
.about{
  width: 800px;
  margin: 0 auto;
}
  .quoteBox {
    width: 68vw;
    margin: 0 auto;
  }

  span {
    display: inline-flex;
    float: right;
  }

  .parallax {
    /* The image used */
    background-image: url("../assets/marcusaurelius.jpg");

    /* Set a specific height */
    height: 600px;
    width: 100vw;

    /* Create the parallax scrolling effect */
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }

  .container {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .title {
    font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
      'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
  }

  .subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
  }

  .links {
    padding-top: 15px;
  }

</style>
