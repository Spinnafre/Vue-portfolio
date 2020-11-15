<template>
  <section id="sobre-mim">
    <v-carousel
      cycle
      height="400"
      hide-delimiter-background
      show-arrows-on-hover
    >
      <v-carousel-item v-for="(slide, i) in slides" :key="i" :src="slide.img">
        <v-sheet height="100%">
          <v-row class="fill-height" align="center" justify="center">
            <div class="display-3 slider">
              <img :src="slide.img" v-show="slide.img" alt="" srcset="" />
              <p>{{ slide.desc }}</p>
            </div>
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
  </section>
</template>
<script>
export default {
  data() {
    return {
      colors: [
        "indigo",
        "warning",
        "pink darken-2",
        "red lighten-1",
        "deep-purple accent-4",
      ],
      slides: [
        {
          desc:
            "Sou apaixonado por tecnologias, manter atualizado e aprender coisas novas é o meu maior hobbie.",
          img:
            "https://fiverr-res.cloudinary.com/images/t_main1,q_auto,f_auto,q_auto,f_auto/gigs/103514756/original/52df9ad105e1ab1c614c2430a1b432cb09a4c33a/create-web-apps-with-reactjs-and-redux-frameworks.png",
        },
        {
          desc:
            "Tecnologias: Node, Javascript, React, React Native, Vue, Banco de dados (SQL, NOSQL)...",
          img:
            "https://images.pexels.com/photos/943096/pexels-photo-943096.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500",
        },
      ],
    };
  },
};
</script>

<style>
p {
  font-size: 22px;
}
.slider {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.slider img {
  max-width: 40%;
}
.theme--dark.v-sheet {
    background-color: transparent;
    color: #fff;
}



</style>