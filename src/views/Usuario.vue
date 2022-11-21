<template>
  <v-container>
    <h2 class="text-h5 text-center px-6 ma-3">Pontos Usuario</h2>
    <v-simple-table>
      <template v-slot:default>
        <thead>
          <tr>
            <th colspan="2" class="text-left">Nome</th>
            <th colspan="2" class="text-left">Pontos total</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>
              <span class="pl-2"> {{ username }} </span>
            </td>
            <td>
              <span colspan="pl-4" class="text-left">{{ pontosTotal }}</span>
            </td>
            <td>
              <v-btn color="green" dark> Trocar pontos </v-btn>
            </td>
          </tr>
        </tbody>
      </template>
    </v-simple-table>

    <h2 class="text-h5 text-center px-6 ma-3">Locais visitados pelo Usuario</h2>
    <v-simple-table>
      <template v-slot:default>
        <thead>
          <tr>
            <th colspan="2" class="text-left">Local</th>
            <th colspan="2" class="text-left" alt="Selecione os visitados">
              Selecione os locais visitados
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(coleta, index) of listaColeta" :key="coleta.id">
            <td>{{ index + 1 }}</td>
            <td>
              <span class="pl-4">{{ coleta.nome }}</span>
            </td>
            <td>
              <div class="ms-8">
                <v-btn
                  v-on:click="contadorSomar"
                  color="green"
                  fab
                  x-small
                  dark
                >
                  <v-icon>mdi-plus</v-icon>
                </v-btn>
              </div>
            </td>
          </tr>
        </tbody>
      </template>
    </v-simple-table>
  </v-container>
</template>

<script>
export default {
  name: "Usuario",
  data() {
    return {
      username: String,
      listaColeta: [
        {
        "key": 0,
        "nome":"Verdão - Coleta Inteligente",
        "categorias":"Plástico, Papel e Vidro",
        "imagem":"https://web.arapiraca.al.gov.br/wp-content/uploads/2020/11/Pevs-1024x682.jpg",
        "endereco":"Rua Marechal Hermes, 110",
        "cep":"11700-100"
        },
        {
        "key": 1,
        "nome":"Planeta Verde SA",
        "categorias":"Orgânico e Metal",
        "imagem":"https://www.manaus.am.gov.br/wp-content/uploads/2022/09/FOTO-ANTONIO-PEREIRA-2-1536x1024.jpg",
        "endereco":"Av Kennedy, 2540",
        "cep":"11703-250"
        }
      ],
      contador: 0,
      pontosTotal: 0,
    };
  },
  methods: {
    contadorSomar() {
      this.contador += 1;
      this.somaPontosTotal();
    },
    somaPontosTotal() {
      this.pontosTotal = this.contador * 10; //Usuario recebe 10 pontos a cada visita um dos pontos de coelta coletiva para trocar por produto ecologicos de parceiros
    },
  },

  created() {
    // fetch("https://it3kjy-default-rtdb.firebaseio.com/coletaSeletiva.json")
    //   .then((response) => response.json())
    //   .then((json) => {
    //     this.listaColeta = json;
    //     console.log(this.listaColeta);
    //   });
  },
  mounted() {
    this.username = this.$store.state.user.nome;
  },
};
</script>

<style scoped>
</style>