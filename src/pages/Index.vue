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
</style>
