<template>
  <div class="painel">
    <div :class="topicoMarcado()">
      <p>{{ numero }}</p>
      <span v-show="marcador == false">|</span>
      <p>{{ titulo }}</p>
    </div>
    <div class="tipo-trilha">
      <p v-if="marcador">{{ trilhaTexto }}</p>
      <p v-else>Selecione um item antes</p>
    </div>
    <div class="lista-image">
      <div v-show="marcador" class="lista-itens">
        <div class="item" v-for="cadeira in trilha" :key="cadeira">
          <p>{{ cadeira }}</p>
        </div>
      </div>
      <img v-show="marcador" :src="image" />
    </div>
  </div>
</template>
<script>
export default {
  props: {
    numero: { type: Number },
    titulo: { type: String },
    trilhaTexto: { type: String },
    marcador: { type: Boolean },
    image: { type: String },
    trilha: { type: Array },
  },
  methods: {
    topicoMarcado() {
      return this.marcador == true ? "topico-marcador-true" : "topico-marcador";
    },
  },
};
</script>
<style>
.painel {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0px;
  margin-top: 60px;
}
.topico-marcador {
  display: flex;
}
.topico-marcador-true {
  display: flex;
}
.topico-marcador p:nth-of-type(1) {
  width: 32px;
  height: 32px;
  border-radius: 16px;
  border: 1px solid #ffffff;
  background-color: rgba(0, 0, 0, 0);
  padding-top: 5px;
  color: white;
}
.topico-marcador-true p:nth-of-type(1) {
  width: 32px;
  height: 32px;
  border-radius: 16px;
  background-color: #ec2353;
  padding-top: 6px;
  color: white;
}
.topico-marcador-true span {
  color: white;
  position: relative;
  left: -18px;
  top: 55px;
}
.topico-marcador-true p:nth-of-type(2) {
  color: white;
  position: relative;
  left: 25%;
  top: 5px;
}
.topico-marcador span {
  color: white;
  position: relative;
  left: -18px;
  top: 55px;
}
.topico-marcador p:nth-of-type(2) {
  color: white;
  position: relative;
  left: 25%;
  top: 5px;
}
.tipo-trilha {
  position: relative;
  left: 55px;
  top: -20px;
}
.tipo-trilha p {
  color: white;
}
.lista-itens {
  width: 510px;
  background-color: white;
}
.lista-itens .item {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding-left: 15px;
  width: 100%;
  height: 56px;
  border-bottom: 1px solid #ccc;
}
.lista-itens .item p {
  margin: 0;
  text-align: left;
}
.lista-image {
  display: flex;
  justify-content: space-between;
}
.lista-image img {
  margin-left: 100px;
  max-height: 335px;
}
</style>