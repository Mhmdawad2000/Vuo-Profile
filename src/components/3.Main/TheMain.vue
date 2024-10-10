<template>
  <main class="flex">
    <section class="flex left-section">
      <button ref="button0" @click="targgetButtons(0)" class="active">
        All Project
      </button>
      <button ref="button1" @click="targgetButtons(1)" class="">
        Html & Css
      </button>
      <button ref="button2" @click="targgetButtons(2)" class="">
        JavaScript
      </button>
      <button ref="button3" @click="targgetButtons(3)" class="">
        React & MUI
      </button>
      <button ref="button4" @click="targgetButtons(4)" class="">
        Node & Express
      </button>
    </section>
    <section class="flex right-section">
      <template v-for="(item, i) in array" :key="i">
        <div
          v-if="item.catogary == this.fillter || this.fillter == 'all'"
          class="parent-artical"
        >
          <article class="card">
            <img :src="item.imagePath" alt="no image" />
            <div class="box">
              <h1 class="title">{{ item.title }}</h1>
              <p class="sub-title">{{ item.subtitle }}</p>
              <div class="flex icons">
                <div style="gap: 11px" class="flex">
                  <a class="icon-link" href=""></a>
                  <a class="icon-github" href=""> </a>
                </div>
                <a class="link flex" href=""
                  >more<span
                    style="align-self: end; font-size: 0.8rem; margin-left: 4px"
                    class="icon-arrow-right"
                  ></span
                ></a>
              </div>
            </div>
          </article>
        </div>
      </template>
    </section>
  </main>
</template>
<script>
export default {
  data() {
    return {
      fillter: "all",
      array: [
        {
          imagePath: "/images/1.jpg",
          catogary: "html&css",
          title: "Steps To Improve HTML",
          subtitle:
            "HTML is a powerful and versatile markup language that allows you to create and structure web pages",
        },
        {
          imagePath: "/images/2.jpg",
          catogary: "react&mui",
          title: "React Component Libraries",
          subtitle:
            "React UI component libraries are collections of ready-to-use or pre-coded user ......",
        },
        {
          imagePath: "/images/3.jpg",
          catogary: "js",
          title: "Best Developer Skills",
          subtitle:
            "Are you an aspiring programmer, or perhaps just interested in learning more about the programming field?",
        },
        {
          imagePath: "/images/4.jpg",
          catogary: "js",
          title: "Best Developer Skills.js",
          subtitle:
            "The best skills for JavaScript Developers include JavaScript Proficiency, HTML/CSS Expertise......",
        },
        {
          imagePath: "/images/5.jpg",
          catogary: "react&mui",
          title: "Free MUI Kit",
          subtitle:
            "Free UI Kit with elegant and modern style will help you to quickly create your own design.",
        },
        {
          imagePath: "/images/6.jpg",
          catogary: "node&express",
          title: "How To Master Express JS",
          subtitle:
            "Easily define routes and endpoints for APIs, pages, error handling and more. Use handy path params, route matching, and chained route handlers.",
        },
        {
          imagePath: "/images/7.jpg",
          catogary: "html&css",
          title: "Html and Css",
          subtitle:
            "With CSS, you can control the color, font, the size of text, the spacing between elements.",
        },
        {
          imagePath: "/images/8.jpg",
          catogary: "js",
          title: "Introduction to JavaScript",
          subtitle:
            "JavaScript and Java are completely different languages, both in concept and design.",
        },
        {
          imagePath: "/images/9.jpg",
          catogary: "html&css",
          title: "Make Your CSS Style",
          subtitle:
            "The external style sheet can be written in any text editor. The file must not contain any HTML code, and must be saved with a .css extension.",
        },
        {
          imagePath: "/images/10.jpg",
          catogary: "react&mui",
          title: "Tested React Solutions",
          subtitle:
            "Web-based applications can be tested using a variety of methods. These testing methods have been combined.",
        },
        {
          imagePath: "/images/11.jpg",
          catogary: "html&css",
          title: "HTML Guia Definitivo",
          subtitle:
            "HTML consists of a series of elements, which you use to enclose, wrap, or mark up different parts of content.",
        },
        {
          imagePath: "/images/12.jpg",
          catogary: "js",
          title: "The Big Javascript Guide",
          subtitle:
            "The JavaScript Guide shows you how to use JavaScript and gives an overview of the language.",
        },
        {
          imagePath: "/images/13.jpg",
          catogary: "node&express",
          title: "What Is Node.js",
          subtitle:
            "As an asynchronous event-driven JavaScript runtime, Node.js is designed to build scalable network applications",
        },
      ],
    };
  },
  methods: {
    targgetButtons(n) {
      let item = "";
      let now_active = "";
      for (let index = 0; index < 5; index++) {
        item = "button" + index;
        now_active = this.$refs[item];
        now_active.classList.remove("active");
      }
      item = "button" + n;
      let make_active = this.$refs[item];
      make_active.classList.add("active");
      switch (n) {
        case 1:
          this.fillter = "html&css";
          break;
        case 2:
          this.fillter = "js";
          break;
        case 3:
          this.fillter = "react&mui";
          break;
        case 4:
          this.fillter = "node&express";
          break;
        default:
          this.fillter = "all";
          break;
      }
    },
  },
};
</script>
<style lang="css">
@import "@/components/3.Main/TheMain.css";
</style>
