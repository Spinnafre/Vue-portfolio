<template>
  <section class="proj-section" id="projetos">
    <v-container>
      <v-row>
        <v-col>
          <h1>Projetos</h1>
        </v-col>
      </v-row>
      <v-row class="main-cards">
        <v-col class="container-cards">
          <v-card
            class="mb-8"
            max-width="344"
            v-for="card in cards"
            :key="card.id"
          >
            <v-img :src="card.img" height="200px"></v-img>

            <v-card-title> {{ card.name }} </v-card-title>

            <v-card-subtitle> Feito por: Spinnafre </v-card-subtitle>

            <v-card-actions>
              <v-card-text>
                <v-chip-group
                  active-class="deep-purple accent-4 white--text"
                  column
                >
                  <v-chip v-for="tag in card.tags" :key="tag">{{ tag }}</v-chip>
                </v-chip-group>
              </v-card-text>

              <v-spacer></v-spacer>

              <v-btn icon @click="card.show = !card.show">
                <v-icon>{{
                  card.show ? "mdi-chevron-up" : "mdi-chevron-down"
                }}</v-icon>
              </v-btn>
            </v-card-actions>

            <v-expand-transition>
              <div v-show="card.show">
                <v-divider></v-divider>

                <v-card-text>
                  {{ truncate(card.coment) }}
                </v-card-text>
              </div>
            </v-expand-transition>
            <v-card-actions>
              <v-btn color="deep-purple lighten-2" text :href="card.link">
                Visitar
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>


<script>
export default {
  data: () => ({
    cards: [
      {
        id: 0,
        show: false,
        name: "DAVICOMMERCE",
        coment:
          "DAVICOMMERCE é um projeto Open Source desenvolvido utilizando as tecnologias Javascript, Node, MongoDB e React.",
        link: "https://github.com/Spinnafre/DAVICOMMERCE",
        img: "https://github.com/Spinnafre/DAVICOMMERCE/raw/master/Home.gif",
        tags: ["react", "node", "redux", "mongoose"],
      },
      {
        id: 1,
        show: false,
        name: "Save Live",
        coment:
          "O saveLife é um projeto que visa conectar pessoas que desejam fazer contribuições monetárias a ONG's (Organizações não governamentais) que precisam de ajuda.",
        link: "https://github.com/Spinnafre/SAVE-LIVE",
        img:
          "https://github.com/Spinnafre/SAVE-LIVE/raw/master/saveLifeAPP.png",
        tags: ["JS", "NODE", "AXIOS", "REACT", "LEAFLET"],
      },
      {
        id: 2,
        show: false,
        name: "MY CRUD",
        coment:
          "Com base nos estudos sobre as funcionalidades do React, NodeJs, Bootstrap e Responsividade, resolvi criar uma aplicação para treinar programação web.",
        link: "https://github.com/Spinnafre/myCrud",
        img: "https://github.com/Spinnafre/myCrud/raw/master/anigif.gif",
        tags: ["REACT", "NODE", "BOOTSTRAP"],
      },
      
    ],
  }),
  methods: {
    truncate(string) {
      if (string.length > 200) {
        return string.slice(0, 200) + "...";
      }
      return string;
    },
  },
};
</script>

<style scoped>
.proj-section {
  /* background-color:#F8C471 ; */
  border: none;
  /* border-radius: 8px; */
}
.col p,

.container-cards {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  max-width: 1200px;
  /* align-items: center; */
  flex-wrap: wrap;
  height: 100%;
}
.main-cards{
  display: flex;
  justify-content: center;
  align-items: center;
}

.v-card {
  margin: 0;
  padding: 0;
  height: 100%;
  
}
.proj-section{
  background-color:#7983b1;
  border: 0;
}
.proj-section h1{
  color: cornsilk;
}
.v-card__title{
  color: #232323;
  font-weight: bold;
}

</style>