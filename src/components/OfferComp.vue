<template>
  <div class="offer">
    <h1>What I can Offer you?</h1>
    <p>{{ learnMore }}</p>
    <div class="items">
      <div class="item">
        <!--Empty blocks for design purpose-->
        <div class="rectangleLeft" />
        <img src="@/assets/portfolio/sketches/GIRL.png" alt="sketch">
        <h1>Consulting</h1>
        <button @click="goToContact">Learn More</button>
      </div>
      <div class="item">
        <img src="@/assets/portfolio/sketches/NOTEBOOK.png" alt="sketch">
        <h1>Content Creation</h1>
        <button @click="goToContact">Let's do it</button>
      </div>
      <div class="item">
        <div class="rectangleRight" />
        <img src="@/assets/portfolio/sketches/PHONE.png" alt="sketch">
        <h1>Copywriting</h1>
        <button @click="goToContact">I'm in</button>
      </div>
    </div>
    <img src="@/assets/portfolio/sketches/scetch.png" alt="sketch" id="sketch1">
    <img src="@/assets/portfolio/sketches/scetch.png" alt="sketch" id="sketch2">
    <img src="@/assets/portfolio/sketches/scetch.png" alt="sketch" id="sketch3">
  </div>
</template>

<script>
import router from "@/router";

export default {
  name: "OfferComp",
  data() {
    return {
      learnMore: "Learn more about how you, " +
        "your team, or organization can go from beginner to industry" +
        " influencer with real strategies and customized content"
    }
  },
  methods:{
    goToContact(){
      router.push("/contact");
    }
  }
}
</script>

<style lang="scss">



.offer {
  position: relative;
  overflow: hidden;
  padding-top: 30px;

  h1,p,.items{
    position: relative;
    z-index: 10;
  }

  h1 {
    text-align: center;
    text-transform: uppercase;
    color: $global;
    font-family: $mainFont;
    font-weight: 700;
    margin: 35px 0;
  }

  p {
    text-align: center;
    color: black;
    margin: auto;
    width: 35%;
    font-family: $mainFont;
    font-weight: 600;
  }

  .items {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;

    .item {
      width: 30%;
      text-align: center;

      .rectangleLeft {
        height: 60px;
        position: absolute;
        width: 15%;
        background-color: #ECC0B2FF;
        left: 0;
        bottom: 50%;
        z-index: -1;
        transform: translateY(-50%);
      }

      .rectangleRight {
        height: 60px;
        position: absolute;
        width: 15%;
        background-color: #ECC0B2FF;
        right: 0;
        bottom: 50%;
        z-index: -1;
        transform: translateY(-50%);
      }

      img {
        width: 100%;
      }

      h1 {
        font-family: $mainFont;
        text-transform: uppercase;
        font-weight: 600;
        color: $black-color
      }

      button {
        padding: 19px;
        color: white;
        background-color: $global;
        border: none;
        border-radius: 30px;
        text-transform: uppercase;
        font-size: 20px;
        width: 275px;

        &:hover {
          background-color: black;
          color: $global;
          cursor: pointer;
        }
      }
    }
  }

  #sketch1,
  #sketch2,
  #sketch3 {
    position: absolute;
    z-index: 1;
  }

  #sketch1 {
    top: -85px;
    left: -280px;
    transform: rotate(12deg);
  }

  #sketch2 {
    top: -42px;
    right: -301px;
    transform: rotate(172deg);
  }

  #sketch3 {
    bottom: 56px;
    left: -275px;
    transform: rotate(30deg);
  }
}
@media screen and (max-width: 950px) {
  .offer {
    p {
      font-size: 20px;
      width: 85%;
    }

    .items {
      display: flex;
      flex-direction: column;


      .item {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 70% !important;

        h1 {
          color: $black-color
        }
      }
    }
  }
  #sketch1,
  #sketch2,
  #sketch3 {
    display: none;
  }
}
</style>