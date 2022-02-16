<template>
  <div class="home">
    <section class="hero">
      <div class="hero-text container">
        <h4>serwis</h4>
        <hr />
        <h2>
          Rejestracji  <br />
          na rekolekcje oazowe
        </h2>
        <hr />
      </div>
    </section>
  </div>
</template>

<script>

// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {},
};
</script>


<style lang="scss" scoped>

.hero {
  // background-image: url("../assets/pexels-bg.jpg");
  background-attachment: fixed;
  position: relative;
  height: 100vh;


  .hero-text {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-left: 64px;
    color: #FEFEFE;
    h4 {
      text-transform: uppercase;
      font-size: 22px;
      padding-bottom: 4px;
    }

    h2 {
      font-size: 40px;
      @media (min-width: 760px) {
        font-size: 70px;
      }
    }

    hr:nth-child(2) {
      max-width: 365px;
      margin-bottom: 16px;
    }

    hr:nth-child(4) {
      height: 6px;
      border: none;
      max-width: 85px;
      margin-top: 16px;
      background-color: #fefefe75;
    }

  }
}
</style>