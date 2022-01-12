<template>
  <div class="painel">
    <div :class="topicoMarcado()">
      <p>{{ numero }}</p>
      <span>|</span>
      <p>{{ titulo }}</p>
    </div>
    <div class="tipo-trilha">
      <p>{{ trilhaTexto }}</p>
    </div>
    <div class="lista-itens"></div>
  </div>
</template>
<script>
export default {
  props: {
    numero: { type: Number },
    titulo: { type: String },
    trilhaTexto: { type: String },
    marcador: { type: Boolean },
  },
  methods:{
    topicoMarcado(){
      return this.marcador==true? 'topico-marcador-true':'topico-marcador'
    }
  }
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
  background-color: #EC2353;
  padding-top: 5px;
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
  left: 60px;
  top: -20px;
}
.tipo-trilha p {
  color: white;
}
</style>