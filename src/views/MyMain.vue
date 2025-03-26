<template>
  <div class="my-main roboto-light container">
    <TheHeader ref="Header" />
    <TheHero />
    <TheDivider ref="Projects" :text="'Projects'" />
    <TheMain />
    <TheDivider ref="Contact" :text="'Skills'" />
    <TheSkills />
    <TheDivider ref="Contact" :text="'Contact Us'" />
    <TheContact />
    <TheDivider ref="Information" :text="'Information'" />
    <TheFooter />
    <button
      ref="go2upButton"
      @click="scroll2Header"
      class="icon-keyboard_arrow_up scrollbar-top hide"
    ></button>
  </div>
</template>
<script>
import TheHeader from "@/components/1.Header/TheHeader.vue";
import TheHero from "@/components/2.Hero/TheHero.vue";
import TheMain from "@/components/3.Main/TheMain.vue";
import TheSkills from "@/components/4.Skills/TheSkills.vue";
import TheContact from "@/components/5.Contact/TheContact.vue";
import TheFooter from "@/components/6.Footer/TheFooter.vue";
import TheDivider from "@/components/7.Divider/TheDivider.vue";

export default {
  components: {
    TheHeader,
    TheHero,
    TheMain,
    TheSkills,
    TheContact,
    TheFooter,
    TheDivider,
  },
  data() {
    return {
      go2up: false,
    };
  },
  methods: {
    checkGo2Up() {
      if (window.scrollY > "400") {
        this.$refs.go2upButton.classList.add("show");
        this.$refs.go2upButton.classList.remove("hide");
        // this.go2up = true;
      } else {
        this.$refs.go2upButton.classList.add("hide");
        this.$refs.go2upButton.classList.remove("show");
        // this.go2up = false;
      }
    },
    scroll2Header() {
      const HeaderComponent = this.$refs.Header.$el;
      window.scrollTo({
        top: HeaderComponent.offsetTop,
        behavior: "smooth",
      });
    },
  },
  mounted() {
    window.addEventListener("scroll", this.checkGo2Up);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.checkGo2Up);
  },
};
</script>
