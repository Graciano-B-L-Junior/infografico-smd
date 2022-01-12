<template>
  <div id="app">
    <h1>Jornada SMD</h1>
    <div class="topico">
      <p>1</p>
      <p>O que você gosta de fazer?</p>
    </div>
    <div class="cards">
      <card :Titulo="'Resolver Problemas'" :imageSource="imagensPainel[0]"/>
      <card :Titulo="'Jogar'" :imageSource="imagensPainel[1]"/>
      <card :Titulo="'Fazer vídeo'" :imageSource="imagensPainel[2]"/>
      <card :Titulo="'Desenhar'" :imageSource="imagensPainel[3]"/>
    </div>
    <painel :numero="2" :titulo="'Trilhas'" :trilhaTexto="'Você está no caminho da programação'" :marcador="paineisMarcados.painel1"/>
  </div>
</template>

<script>
import Card from './components/Card.vue'
import Painel from './components/trilhas/Painel.vue'
import imagem5 from './assets/images/code1.png'
import imagem4 from './assets/images/desenhar1.png'
import imagem2 from './assets/images/jogar1.png'
import imagem1 from './assets/images/problemas1.png'
import imagem3 from './assets/images/video1.png'
export default {
  name: 'App',
  components:{Card,Painel},
  data(){
    return{
      imagensPainel:[
        imagem1,
        imagem2,
        imagem3,
        imagem4,
        imagem5,
        ],
        paineisMarcados:{painel1:true,painel2:false,painel3:false}
    }
  }
}
</script>

<style>
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  margin-left: 100px;

}
#app h1{
  width: 1058px;
  color: white;
  align-self: flex-start;
  text-align: left;
}
.topico{
  display: flex;
  color: white;
  font-weight: 700;
  align-items: center;
}

.topico p:nth-of-type(1){
  background-color: #EC2353;
  width: 32px;
  height: 32px;
  border-radius: 16px;
  margin-right: 24px;
  box-sizing: border-box;
  padding: 6px;
}
.cards{
  display: flex;
  justify-content: space-between;
  width: 90%;
}

</style>
