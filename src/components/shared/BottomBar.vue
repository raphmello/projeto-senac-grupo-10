<template>
  <div class="app-bottom-bar">
    <v-app-bar hide-on-scroll app>
      <v-spacer />
      <v-toolbar-title><h3><strong>Coleta Seletiva</strong> ♻️</h3></v-toolbar-title>
      <v-spacer />
      <v-tooltip v-if="!$vuetify.theme.dark" bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn v-on="on" v-bind="attrs" color="transparent" small fab @click="darkMode">
            <v-icon class="mr-1">mdi-moon-waxing-crescent</v-icon>
          </v-btn>
        </template>
        <span>Dark Mode Off</span>
      </v-tooltip>

      <v-tooltip v-else bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn v-on="on" v-bind="attrs" color="transparent" small fab @click="darkMode">
            <v-icon>mdi-white-balance-sunny</v-icon>
          </v-btn>
        </template>
        <span>Dark Mode On</span>
      </v-tooltip>
    </v-app-bar>
    <v-bottom-navigation :value="value" color="#6d6d6d" app grow>
      <router-link to="/">
        <v-btn>
          <span>Início</span>

          <v-icon>mdi-home</v-icon>
        </v-btn>
      </router-link>

      <router-link to="/pontosdecoleta">
        <v-btn>
          <span>Locais</span>
          <v-icon>mdi-office-building-marker-outline</v-icon>
        </v-btn>
      </router-link>

      <router-link to="/login">
        <v-btn>
          <span>Login</span>

          <v-icon>mdi-account</v-icon>
        </v-btn>
      </router-link>
    </v-bottom-navigation>
  </div>
</template>


<script>
export default {
  name: "BottomBar",
  data() {
    return {
      value: 0,
    };
  },
  methods: {
  darkMode() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
    }
  }
};
</script>

<style scoped>
    .app-bottom-bar > .botoes{
        display: flex;
        justify-content: center;
    }
    .app-bottom-bar a {
            text-decoration: none;
            display:flex;
            justify-content: center;
            flex-grow: 1;
             
    }
</style>