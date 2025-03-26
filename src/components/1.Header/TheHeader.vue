<template>
  <header class="flex">
    <div />

    <button id="ChangeMode" @click="TarggetMode" class="change-mode icon-sun" />
  </header>
</template>
<script>
export default {
  data() {
    return {
      mode: "dark",
      model: false,
    };
  },
  methods: {
    TarggetModel() {
      if (!this.model) {
        document.getElementById("model").style.display = "block";
        this.model = true;
      } else {
        document.getElementById("model").style.display = "none";
        this.model = false;
      }
    },
    TarggetMode() {
      const peraant2all = document.getElementById("mode");
      const change_mode = document.getElementById("ChangeMode");
      if (this.mode == "light") {
        peraant2all.classList.add("dark");
        peraant2all.classList.remove("light");

        change_mode.classList.add("icon-sun");
        change_mode.classList.remove("icon-moon-o");
      } else {
        peraant2all.classList.add("light");
        peraant2all.classList.remove("dark");

        change_mode.classList.remove("icon-sun");
        change_mode.classList.add("icon-moon-o");
      }
      this.mode = this.mode == "dark" ? "light" : "dark";
      localStorage.setItem("mode", this.mode);
    },

    SavedMode() {
      const peraant2all = document.getElementById("mode");
      const change_mode = document.getElementById("ChangeMode");
      if (this.mode == "light") {
        peraant2all.classList.remove("dark");
        peraant2all.classList.add("light");

        change_mode.classList.remove("icon-sun");
        change_mode.classList.add("icon-moon-o");
      } else {
        peraant2all.classList.remove("light");
        peraant2all.classList.add("dark");

        change_mode.classList.remove("icon-sun");
        change_mode.classList.add("icon-moon-o");
      }
    },
  },
  mounted() {
    let theme = localStorage.getItem("mode");
    if (theme) {
      this.mode = theme;
    } else {
      this.mode = "dark";
    }
    this.SavedMode();
  },
};
</script>

<style lang="css">
@import "@/components/1.Header/TheHeader.css";
</style>
