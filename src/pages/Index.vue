<template>
  <Layout>
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <About />
    <Projects />
    <Formation />
    <Contact />
  </Layout>
</template>

<script>
import About from "@/components/About.vue";
import Projects from "@/components/Projects.vue";
import Formation from "@/components/Formation.vue";
import Contact from "@/components/Contact.vue";

export default {
  metaInfo: {
    title: "Hello",
  },
  components: {
    About,
    Projects,
    Formation,
    Contact,
  },
};
</script>

<style>

.home-links a {
  margin-right: 1rem;
}
/* width */
::-webkit-scrollbar {
  width: 10px;

}

/* Track */
::-webkit-scrollbar-track {
  background: #f1f1f1; 
}
 
/* Handle */
::-webkit-scrollbar-thumb {
  background: #888; 
  height: 20px;
  border-radius: 4px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555; 
}
html {
  scroll-behavior: smooth !important;
}

.container,.v-main-wrap{
  padding: 0;
}
</style>
