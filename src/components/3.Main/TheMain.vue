<template>
  <main class="flex">
    <section class="flex left-section">
      <button ref="button0" @click="targgetButtons(0)" class="active">
        All Project
      </button>
      <button ref="button1" @click="targgetButtons(1)" class="">
        Html & Css
      </button>
      <button ref="button2" @click="targgetButtons(2)" class="">Backend</button>
      <button ref="button3" @click="targgetButtons(3)" class="">
        Livewire
      </button>
      <button ref="button4" @click="targgetButtons(4)" class="">
        Firebase
      </button>
      <button ref="button5" @click="targgetButtons(5)" class="">
        RabbitMQ
      </button>

      <button ref="button6" @click="targgetButtons(6)" class="">Redis</button>
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
                  <a
                    v-if="item.link"
                    class="icon-link"
                    target="_blank"
                    :href="item.link"
                  ></a>
                  <a class="icon-github" target="_blank" :href="item.github">
                  </a>
                </div>
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
          link: "https://mhmdawad2000.github.io/muhamed/",
          github: "https://github.com/Mhmdawad2000/muhamed.git",
          imagePath: "/images/1.png",
          catogary: "html&css",
          title: "Simple HTML Project",
          subtitle: "Simple pages in HTML and CSS.",
        },
        {
          github: "https://github.com/Mhmdawad2000/Msarati.git",
          imagePath: "/images/2.jpg",
          catogary: "Backend",
          title: "Msarati Back-end Laravel Project",
          subtitle:
            "Msarati is a project developed to make it easier for customers to request a taxi and track its route in real-time.",
        },
        {
          github: "https://github.com/Mhmdawad2000/Betonna.git",
          imagePath: "/images/3.avif",
          catogary: "Backend",
          title: "Betonna Back-end Laravel Project",
          subtitle:
            "Betonna is a project developed to facilitate the customer's search for real estate to buy or sell, or for a residential complex to buy or sell.....",
        },
        {
          github: "https://github.com/Mhmdawad2000/Socio.git",
          imagePath: "/images/4.png",
          catogary: "Livewire",
          title: "Socio Laravel-Livewire Project",
          subtitle:
            "This platform applecation have profile for any user use livewire and laravel.",
        },
        {
          github: "https://github.com/Mhmdawad2000/Firebase-Larevel.git",
          imagePath: "/images/5.jpg",
          catogary: "Firebase",
          title: "Firebase-Larevel Project",
          subtitle: "Connect laravel with firebsase database.",
        },
        {
          github: "https://github.com/Mhmdawad2000/RabbitMQ-Laravel.git",
          imagePath: "/images/6.jpg",
          catogary: "RabbitMQ",
          title: "RabbitMQ-Larevel Project",
          subtitle: "Use RabbitMQ events with laravel.",
        },
        {
          github: "https://github.com/Mhmdawad2000/Redis-Laravel.git",
          imagePath: "/images/7.webp",
          catogary: "Redis",
          title: "Redis-Larevel Project",
          subtitle: "Use Redis jops and queus with laravel.",
        },
        {
          github: "https://github.com/Mhmdawad2000",
          imagePath: "/images/8.png",
          catogary: "all",
          title: "Show more Projects",
          subtitle: "Visit my GITHUB to show more..",
        },
      ],
    };
  },
  methods: {
    targgetButtons(n) {
      let item = "";
      let now_active = "";
      for (let index = 0; index < 7; index++) {
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
          this.fillter = "Backend";
          break;
        case 3:
          this.fillter = "Livewire";
          break;
        case 4:
          this.fillter = "Firebase";
          break;
        case 5:
          this.fillter = "RabbitMQ";
          break;
        case 6:
          this.fillter = "Redis";
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
