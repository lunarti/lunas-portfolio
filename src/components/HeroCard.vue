<template>
  <main>
    <div class="hero-text">
      <h1 ref="greeting">Olá,</h1>
      <h2 ref="name">Eu sou Victor.</h2>
    </div>
    
    <aside class="hero-image lg:ml-20 mb-10 ">
      <img
        @mouseenter="imagePopup"
        @mouseleave="imagePopdown"
        ref="img"
        src="../assets/1630854242052.jpeg"
      />
    </aside>
  </main>
</template>

<script>
import { TimelineLite } from "gsap/dist/gsap";
export default {
  name: "HeroCard",
  mounted() {
    const greeting = this.$refs.greeting;
    const name = this.$refs.name;
    const img = this.$refs.img;
    const timeline = new TimelineLite();
    const tl = new TimelineLite();
    timeline.from(greeting, {
      y: -20,
      opacity: 0,
      duration: 0.5,
      ease: "back.out(1.7)",
    });
    timeline.from(name, {
      y: -20,
      opacity: 0,
      duration: 0.5,
      ease: "back.out(1.7)",
    });
    tl.from(img, {
      y: -80,
      opacity: 0,
      duration: 1,
      ease: "back.out(1.7)",
    });
  },
  methods: {
    imagePopup() {
      const img = this.$refs.img;
      const tl = new TimelineLite();
      tl.to(img, {
        boxShadow: "0px 0px 15px 0px rgba(0,0,0,0.55)",
        scale: 1.1,
      });
    },
    imagePopdown() {
      const img = this.$refs.img;
      const tl = new TimelineLite();
      tl.to(img, {
        scale: 1,
      });
    },
    goToMe() {
      document.getElementById("me").scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>

<style scoped>
main {
  display: flex;
  flex-flow: row wrap-reverse;
  justify-content: center;
  width: 100%;
}
h1 {
  margin: 0;
  font-weight: 300;
  font-size: clamp(32px, 4vw, 52px);
}
h2 {
  margin: 0;
  font-size: clamp(100px, 8vw, 140px);
  font-weight: 900;
}
img {
  border: 10px solid rgb(87, 63, 190);
  border-radius: 50%;
  width: clamp(200px, 15vw, 20vw);
}


</style>