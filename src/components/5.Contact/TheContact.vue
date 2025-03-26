<template>
  <div class="">
    <section class="contact-us">
      <div class="up-section">
        <h1 class="title">
          <span class="icon-envelope"></span>
          Contact us
        </h1>
      </div>
      <div class="down-section flex">
        <div class="border-animation">
          <div action="" class="left-section">
            <div style="color: gray; font-size: 20px">
              <span
                style="margin: 1rem; font-size: 17px"
                class="icon-envelope"
              ></span
              ><span style="font-size: 12px">muhamedawad2000@gmail.com</span>
            </div>
            <div style="color: gray; font-size: 20px">
              <span style="margin: 1rem" class="icon-mobile"></span
              ><span>+963 998410169</span>
            </div>
            <div style="color: gray; font-size: 20px">
              <span style="margin: 1rem" class="icon-location2"></span
              ><span>Damascus,Syria</span>
            </div>
          </div>
        </div>
        <div ref="ContactAnimation" class="animation"></div>
      </div>
    </section>
  </div>
</template>
<script>
import lottie from "lottie-web";
import animationData from "@/assets/animation/Contact.json";

export default {
  mounted() {
    this.animation = lottie.loadAnimation({
      container: this.$refs.ContactAnimation,
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
@import "@/components/5.Contact/TheContact.css";
</style>
