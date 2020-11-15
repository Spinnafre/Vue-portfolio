<template>
  <section class="proj-section" id="projetos">
    <v-container>
      <v-row>
        <v-col>
          <h1>PROJETOS</h1>
        </v-col>
      </v-row>
      <v-row>
        <v-col  class="container-cards">
          <v-card
            class="mb-8"
            max-width="344"
            v-for="card in cards"
            :key="card.id"
          >
            <v-img
              src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
              height="200px"
            ></v-img>

            <v-card-title> {{ card.name }} </v-card-title>

            <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle>

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
                  {{  truncate(card.coment)}}
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
        name: "Davi Commerce",
        coment: "Projeto desenvolvido visando construir um mini ecommerce",
        link: "https://github.com/Spinnafre/DAVICOMMERCE",
        tags: ["react", "node", "redux", "mongoose"],
      },
      {
        id: 1,
        show: false,
        name: "To-do",
        coment: "To-do list desenvolvido sem usar frameworks para o frontend",
        link: "https://github.com/Spinnafre/DAVICOMMERCE",
        tags: ["JS", "HTML", "CSS", "LocalStorage"],
      },
      {
        id: 2,
        show: false,
        name: "Animais-UFC",
        coment:
          "Projeto desenvolvido para uma ONG responsável por cuidar dos animais",
        link: "https://github.com/Spinnafre/DAVICOMMERCE",
        tags: ["react", "node", "redux", "mongoose"],
      },
      {
        id: 3,
        show: false,
        name: "Animais-UFC",
        coment:
          "Projeto desenvolvido para uma ONG responsável por cuidar dos animais",
        link: "https://github.com/Spinnafre/DAVICOMMERCE",
        tags: ["react", "node", "redux", "mongoose"],
      },
    ],
  }),
  methods:{
      truncate(string){
          if(string.length>90){
              return string.slice(0,90)+ '...'
          }
          return string
      }
  }
};
</script>

<style scoped>
.proj-section {
  background-color: #fafafa;
  border: solid 2px #ebebeb;
  border-radius: 8px;
}
.col p,
h1 {
  color: rgb(48, 48, 48);
}
.container-cards{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    flex-wrap: wrap;
}
.v-image{
    filter:grayscale(100%)
}

</style>