<template>
  <section id="formação">
    <v-container>
      <v-row>
        <v-col >
          <h1>Formação</h1>
        </v-col>
      </v-row>
      <v-row>
        <v-col  class="d-flex flex-column align-center justify-center">
          <v-timeline>
            <v-timeline-item
              v-for="(year, i) in years"
              :key="i"
              :color="year.color"
              small
            >
              <template v-slot:opposite>
                <span
                  :class="`headline font-weight-bold ${year.color}--text`"
                  v-text="year.year"
                ></span>
              </template>
              <div class="py-4">
                <h2
                  :class="`headline font-weight-light mb-4 ${year.color}--text`"
                >
                  {{year.title}}
                </h2>
                <div>
                  {{year.description}}
                </div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>
<script>
  export default {
    data: () => ({
      years: [
        {
          color: 'cyan',
          year: '2018',
          title:'Curso',
          description:'Curso técnico de Finanças'
        },
        {
          color: 'green',
          year: '2018',
          title:'Ensino médio',
          description:'Ensimo médio Completo'
        },
        {
          color: 'pink',
          year: '2019',
          title:'Universidade',
          description:'Sistemas e mídias digitais - UFC'
        },

      ],
    }),
  }
</script>