<template>
  <div id="app">
    <h1>Jornada SMD</h1>
    <div class="topico">
      <p>1</p>
      <p>O que você gosta de fazer?</p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
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

</style>
