<template>
  <div class="bg-black h-screen px-6 py-12">
    <h2 ref="title" class="text-white opacity-o font-exo text-5xl mb-4" style="transform: translateY(30px)">MY WORK</h2>

    <div class="flex space-x-4">
      <div ref="projects" class="w-full opacity-0" style="transform: translateX(30px)" v-for="project in projects"
        :key="project.title">
        <nuxt-link to="/">
          <img :src="project.image.url" class="object-cover" style="height: 70vh" :alt="project.title">
          <p class="text-white font-space-mono text-xl">{{ project.title }}</p>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import iphone from '~/assets/iphone.jpg';
import astronaut from '~/assets/astronaut.jpg';
import spaceX from '~/assets/launch.jpg';
import gsap from 'gsap';

export default {
  data() {
    return {
      projects: [
        {
          image: {
            url: iphone
          },
          title: 'iPhone'
        },
        {
          image: {
            url: astronaut
          },
          title: 'NASA'
        },
        {
          image: {
            url: spaceX
          },
          title: 'SpaceX'
        },
        {
          image: {
            url: iphone
          },
          title: 'MacBook'
        },
        {
          image: {
            url: astronaut
          },
          title: 'Astronaut'
        },
        {
          image: {
            url: spaceX
          },
          title: 'Launch'
        }
      ]
    }
  },
  mounted() {
    gsap.to(this.$refs.title, {
      opacity: 1,
      duration: 2,
      y: 0,
      ease: 'expo'
    });

    gsap.to(this.$refs.projects, {
      opacity: 1,
      duration: 2,
      stagger: .1,
      x: 0,
      ease: 'expo',
      delay: 0.3
    })
  }
}
</script>
