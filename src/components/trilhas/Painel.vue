<template>
  <div class="painel">
    <div class="topico">
      <p>{{ numero }}</p>
      <span>|</span>
      <p>{{ titulo }}</p>
    </div>
    <div class="tipo-trilha">
        <p>{{trilhaTexto}}</p>
    </div>
    <div class="lista-itens"></div>
  </div>
</template>
<script>
export default {
  props: ["numero", "titulo",'trilhaTexto'],
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
.topico p:nth-of-type(1){
    width: 32px;
    height: 32px;
    border-radius: 16px;
    border: 1px solid #FFFFFF;
    background-color: rgba(0, 0, 0, 0);
}
.topico span{
    position: relative;
    left: -42px;
    top: 35px;
}
.tipo-trilha{
    position: relative;
    left: 60px;
    top: -20px;
}
.tipo-trilha p{
    color: white;
}
</style>