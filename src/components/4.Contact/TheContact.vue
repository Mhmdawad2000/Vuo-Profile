<template>
  <div class="">
    <section class="contact-us">
      <div class="up-section">
        <h1 class="title">
          <span class="icon-envelope"></span>
          Contact us
        </h1>
        <p class="sub-title">
          Lorem ipsum dolor sit amet consectetur adipisicing elit.
        </p>
      </div>
      <div class="down-section flex">
        <div class="border-animation">
          <form action="" class="left-section">
            <div class="flex">
              <label for="email">Email Addreess:</label>
              <input required type="email" name="email" id="email" />
            </div>
            <div style="margin-top: 24px" class="flex">
              <label for="textarea">Your Message:</label>
              <textarea required name="textarea" id="textarea"></textarea>
            </div>
            <button class="submit">Submit</button>
          </form>
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
@import "@/components/4.Contact/TheContact.css";
</style>
