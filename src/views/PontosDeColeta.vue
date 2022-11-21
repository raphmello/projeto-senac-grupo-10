  <template>
  <div>
    <v-container>
      <PontosDeColetaCard
        v-for="pontoDeColeta in pontosDeColeta"
        :key="pontoDeColeta.id"
        :nome="pontoDeColeta.nome"
        :categorias="pontoDeColeta.categorias"
        :imagem="pontoDeColeta.imagem"
        :endereco="pontoDeColeta.endereco"
        :cep="pontoDeColeta.cep"
      ></PontosDeColetaCard>
    </v-container>
  </div>
</template>

<script>
import PontosDeColetaCard from "../components/PontoDeColetaCard";
export default {
  components: {
    PontosDeColetaCard,
  },
  methods: {},
  data() {
    return {
      pontosDeColeta: [
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
    };
  }
};
</script>

<style>
</style>