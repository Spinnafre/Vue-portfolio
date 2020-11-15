<template>
  <v-app>
    <v-navigation-drawer permanent width="230px" fixed>
      <v-list-item>
        <v-list-item-avatar>
          <v-img
            src="https://avatars2.githubusercontent.com/u/61525268?s=460&u=b66a852f0a5808ec463be41555fe28c2ff6d3e1a&v=4"
          ></v-img>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title class="title"> Davi Silva</v-list-item-title>
          <v-list-item-subtitle> Software Developer</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          :to="`#${item.title.toLowerCase().replace(' ', '-')}`"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container>
        <slot />
      </v-container>
    </v-main>
  </v-app>
</template>
<script>
export default {
  data() {
    return {
      items: [
        { title: "Sobre mim", icon: "mdi-account-box-outline" },
        { title: "Projetos", icon: "mdi-apps" },
        { title: "Formação", icon: "mdi-school-outline" },
        { title: "Contato", icon: "mdi-chat-outline" },
      ],
      right: null,
    };
  },
};
</script>
<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>


<style >

.v-application--wrap {
  flex-direction: row;
  scroll-behavior: smooth;
}

html{
  scroll-behavior: smooth;
}
.v-main {
  flex: 1 0;
  margin-left: 240px;
}
</style>

