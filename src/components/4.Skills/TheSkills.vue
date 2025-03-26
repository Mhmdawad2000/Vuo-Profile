<template>
  <main class="flex">
    <section class="flex left-section">
      <div v-for="(item, i) in array" :key="i" class="skill">
        {{ item }}
      </div>
    </section>
  </main>
</template>
<script>
export default {
  data() {
    return {
      array: [
        "LiveWire",
        "Tailwindcss",
        "Bootstrap",
        "AJAX",
        "Software Engineering",
        "Creational Design Patterns",
        "Algorithms",
        "Problem Solving",
        "OOP",
        "MVC Model",
        "Microsoft Office",
        "JSON",
        "PHP",
        "MYSQL",
        "Laravel",
        "Xampp",
        "Communication",
        "Postman",
        "Self-Development",
        "Team Playing",
        "Git & GitHub",
        "Data Structure",
      ],
    };
  },
};
</script>
<style lang="css">
@import "@/components/4.Skills/TheSkills.css";
</style>
