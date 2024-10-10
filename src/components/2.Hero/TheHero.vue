<template>
  <section class="hero flex">
    <div class="left-section">
      <div class="perant-avatar flex">
        <img src="../../../public/profile.jpg" alt="" class="avatar" />
        <div class="icon-verified"></div>
      </div>
      <h1 class="title">
        <span>Software </span>
        <span>Engineer </span>
        <span>,FullStack </span>
        <span>Developer </span>
        <span>,Problems </span>
        <span>Solver </span>
        <span>,Best </span>
        <span>Creator </span>
        <span>Of </span>
        <span>Algorithms</span>
      </h1>
      <p class="sub-title">
        My name is Muhamed Khyr Awad.I am FullStack developer.<br />With a
        four-year immersion in technology, I've specialized as a back-end
        developer, proficient in the Laravel framework and MVC architecture.
        I've specialized as a front-end developer, proficient in the React
        framework. Through diverse projects, I've refined my skills in system
        development and optimization. Aspiring to transition into a systems
        analyst role post-graduation to leverage my expertise in enhancing
        complex systems
      </p>
      <div class="icons flex">
        <div class="icon icon-github"></div>
        <div class="icon icon-linkedin"></div>
        <div class="icon icon-instagram"></div>
        <div class="icon icon-facebook"></div>
        <div class="icon icon-twitter"></div>
      </div>
    </div>
    <div ref="HeroAnimation" class="right-section animation"></div>
  </section>
</template>
<script>
import lottie from "lottie-web";
import animationData from "@/assets/animation/Hero.json";

export default {
  mounted() {
    this.animation = lottie.loadAnimation({
      container: this.$refs.HeroAnimation,
      loop: true,
      autoplay: true,
      animationData: animationData,
    });
  },
  beforeUnmount() {
    if (this.animation) {
      this.animation.destroy();
    }
  },
};
</script>

<style lang="css">
@import "@/components/2.Hero/TheHero.css";
</style>
