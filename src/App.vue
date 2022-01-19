<template>
  <div id="app">
    <h1>Jornada SMD</h1>
    <div class="topico">
      <p>1</p>
      <p>O que você gosta de fazer?</p>
    </div>
    <div class="cards">
      <card
        @click="indiceTrilhaTexto = 0"
        @atualizaTrilha="mostraTrilha(trilhas.trilhaProg)"
        :Titulo="'Resolver Problemas'"
        :imageSource="imagensPainel[0]"
      />
      <card
        @click="indiceTrilhaTexto = 1"
        @atualizaTrilha="mostraTrilha(trilhas.trilhaJogos)"
        :Titulo="'Jogar'"
        :imageSource="imagensPainel[1]"
      />
      <card
        @click="indiceTrilhaTexto = 2"
        @atualizaTrilha="mostraTrilha(trilhas.trilhaAudiovisual)"
        :Titulo="'Fazer vídeo'"
        :imageSource="imagensPainel[2]"
      />
      <card
        @click="indiceTrilhaTexto = 3"
        @atualizaTrilha="mostraTrilha(trilhas.trilhaDesign)"
        :Titulo="'Desenhar'"
        :imageSource="imagensPainel[3]"
      />
    </div>
    <painel
      :numero="2"
      :titulo="'Trilha'"
      :trilhaTexto="trilhaTexto[indiceTrilhaTexto]"
      :marcador="paineisMarcados.painel1"
      :image="imagensPainel[4]"
      :trilha="trilhaAtual"
    />
  </div>
</template>

<script>
import Card from "./components/Card.vue";
import Painel from "./components/trilhas/Painel.vue";
import imagem5 from "./assets/images/code1.png";
import imagem4 from "./assets/images/desenhar1.png";
import imagem2 from "./assets/images/jogar1.png";
import imagem1 from "./assets/images/problemas1.png";
import imagem3 from "./assets/images/video1.png";
export default {
  name: "App",
  components: { Card, Painel },
  data() {
    return {
      imagensPainel: [imagem1, imagem2, imagem3, imagem4, imagem5],
      indiceTrilhaTexto: 0,
      trilhaTexto: [
        "Você está no caminho da programação",
        "Você está no caminho dos jogos",
        "Você está no caminho Audiovisual",
        "Você está no caminho do Design",
      ],
      paineisMarcados: { painel1: false, painel2: false, painel3: false },
      trilhaAtual: [],
      trilhas: {
        trilhaProg: [
          "ANÁLISE E PROJETO DE SISTEMAS",
          "ESTRUTURA DE DADOS",
          "REDES DE COMPUTADORES",
          "BANCO DE DADOS I",
          "ENGENHARIA DE SOFTWARE",
          "ANÁLISE DE DESEMPENHO",
          "BANCO DE DADOS APLICADO À MULTIMÍDIA",
          "COMPUTAÇÃO MÓVEL E UBÍQUA",
          "DESENVOLVIMENTO DE APLICACOES DISTRIBUÍDAS",
          "FILOSOFIA DA TECNOLOGIA",
          "FRAMEWORKS DE SOFTWARE",
          "GERÊNCIA DE PROJETOS DE SOFTWARE",
          "INSTALAÇÕES MULTIMÍDIA",
          "LABORATÓRIO DE PROGRAMAÇÃO",
          "LINGUAGEM DE PROGRAMAÇÃO SCRIPT",
          "PROGRAMAÇÃO ORIENTADA A OBJETOS",
          "PROGRAMAÇÃO PARA DISPOSITIVOS MÓVEIS",
          "PROGRAMAÇÃO PARA WEB I",
          "SISTEMAS EMBARCADOS",
          "TESTE DE SOFTWARE APLICADO",
        ],
        trilhaDesign: [
          "DESENHO II",
          "FOTOGRAFIA DIGITAL",
          "SEMIÓTICA APLICADA",
          "COMUNICAÇÃO VISUAL II",
          "DESIGN DE SOM",
          "CIBERCULTURA E EDUCAÇÃO: NOVAS PRÁTICAS",
          "COMUNICAÇÃO EM NOVAS MÍDIAS",
          "DESIGN DE IDENTIDADE DE MARCA",
          "DESIGN EMOCIONAL",
          "DESIGN INSTRUCIONAL",
          "EDUCOMUNICAÇÃO",
          "EXPERIMENTOS EM TIPOGRAFIA DIGITAL",
          "GESTÃO DE NEGOCIOS EM MULTIMÍDIA",
          "INTERAÇÃO HUMANO-COMPUTADOR II",
          "LABORATÓRIO DE CRIATIVIDADE",
          "TÉCNICAS DE ANIMAÇÃO ANALÓGICA",
          "TÉCNICAS DE ANIMACAO DIGITAL I",
          "TÉCNICAS DE ANIMAÇÃO 2D",
          "TEORIA E CRÍTICA DO DESIGN",
          "TÓPICOS AVANÇADOS EM DESIGN DE INTERFACES GRÁFICAS",
        ],
        trilhaJogos: [
          "ANÁLISE E PROJETO DE SISTEMAS",
          "ESTRUTURA DE DADOS",
          "SEMIÓTICA APLICADA",
          "BANCO DE DADOS I",
          "ENGENHARIA DE SOFTWARE",
          "INTELIGÊNCIA COMPUTACIONAL APLICADA A JOGOS I",
          "CONCEPÇÃO DE CENÁRIOS E DE PERSONAGENS",
          "CULTURA DE JOGOS",
          "DESENVOLVIMENTO DE JOGOS CASUAIS",
          "DESENVOLVIMENTO DE MATERIAL DIDÁTICO EXPERIMENTAL E TREINAMENTO DE HABILIDADES",
          "DESENVOLVIMENTO DE MOTORES GRÁFICOS",
          "DESIGN DE JOGOS DIGITAIS",
          "FERRAMENTAS DE MODELAGEM TRIDIMENSIONAL I",
          "JOGOS DISTRIBUÍDOS",
          "LABORATÓRIO DE COMPUTAÇÃO GRÁFICA",
          "MATEMÁTICA E FÍSICA PARA JOGOS",
          "PROGRAMAÇÃO PARA JOGOS II",
          "PROTOTIPAÇÃO DE JOGOS TRIDIMENSIONAIS",
          "TÉCNICAS DE ANIMAÇÃO 3D I",
          "PROGRAMAÇÃO PARA JOGOS I",
        ],
        trilhaAudiovisual: [
          "DESENHO II",
          "FOTOGRAFIA DIGITAL",
          "SEMIÓTICA APLICADA",
          "COMUNICAÇÃO VISUAL II",
          "DESIGN DE SOM",
          "MITOLOGIAS UNIVERSAIS",
          "DIFERENÇA E ENFRENTAMENTO PROFISSIONAL NAS DESIGUALDADES SOCIAIS",
          "EDUCAÇÃO, COGNICAO E TECNOLOGIAS DIGITAIS",
          "IDENTIDADE SONORA DE MARCAS",
          "LINGUAGEM AUDIOVISUAL",
          "MITOS E ARQUÉTIPOS",
          "PROCESSAMENTO DIGITAL DE AUDIO",
          "PRODUÇÃO AUDIOVISUAL",
          "PRODUÇÃO AUDIOVISUAL PARA CRIANÇAS E ADOLESCENTES",
          "PROJETOS PARA EDUCAÇÃO ON-LINE",
          "REDAÇÃO PARA MÍDIAS DIGITAIS",
          "SOCIEDADE, CULTURA E TECNOLOGIA",
          "TECNODOCÊNCIA E ANIMAÇÃO",
          "VIDEOGRAFISMO",
        ],
      },
    };
  },
  methods: {
    mostraTrilha(trilha) {
      switch (trilha) {
        case trilha == this.trilhas.trilhaProg:
          this.indiceTrilhaTexto = 0;
          break;
        case trilha == this.trilhas.trilhaJogos:
          this.indiceTrilhaTexto = 1;
          break;
        case trilha == this.trilhas.trilhaAudiovisual:
          this.indiceTrilhaTexto = 2;
          break;
        case trilha == this.trilhas.trilhaDesign:
          this.indiceTrilhaTexto = 3;
          break;
      }
      this.trilhaAtual = trilha;
      this.paineisMarcados.painel1 = true;
      this.paineisMarcados.painel2 = false;
    },
  },
};
</script>

<style>
#app {
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  margin-left: 100px;
}
#app h1 {
  width: 1058px;
  color: white;
  align-self: flex-start;
  text-align: left;
}
.topico {
  display: flex;
  color: white;
  font-weight: 700;
  align-items: center;
}

.topico p:nth-of-type(1) {
  background-color: #ec2353;
  width: 32px;
  height: 32px;
  border-radius: 16px;
  margin-right: 24px;
  box-sizing: border-box;
  padding: 6px;
}
.cards {
  display: flex;
  justify-content: space-between;
  width: 90%;
}
</style>
