<template>
  <Particles
    id="tsparticles"
    :particlesInit="particlesInit"
    :particlesLoaded="particlesLoaded"
    :options="{
      background: {
        color: {
          value: '#ffffff',
        },
        size: 20,
      },
      fpsLimit: 120,
      interactivity: {
        events: {
          onClick: {
            enable: false,
            mode: 'push',
          },
          onHover: {
            enable: true,
            mode: 'repulse',
          },
          resize: true,
        },
        modes: {
          bubble: {
            distance: 400,
            duration: 6,
            opacity: 0.8,
            size: 40,
          },
          push: {
            quantity: 4,
          },
          repulse: {
            distance: 100,
            duration: 0.5,
          },
        },
      },
      particles: {
        color: {
          value: '#000000de',
        },
        links: {
          color: '#000000de',
          distance: 150,
          enable: true,
          opacity: 0.5,
          width: 1,
        },
        collisions: {
          enable: false,
        },
        move: {
          direction: 'none',
          enable: true,
          outMode: 'bounce',
          random: false,
          speed: 2,
          straight: false,
        },
        number: {
          density: {
            enable: true,
            area: 800,
          },
          value: 80,
        },
        opacity: {
          value: 0.5,
        },
        shape: {
          type: 'circle',
        },
        size: {
          random: true,
          value: 5,
        },
      },
      detectRetina: true,
    }"
  >
  </Particles>
</template>

<script>
import { loadFull } from "tsparticles";

export default {
  name: "animatedHeader",
  props: ["pageContent"],
  methods: {
    particlesInit: async (engine) => {
      console.log(engine);
      await loadFull(engine);
    },
    particlesLoaded: async (container) => {
      console.log("Particles container loaded", container);
    },
  },
};
</script>
<style>
#particles-js {
  position: fixed;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: 50% 50%;
}
</style>
