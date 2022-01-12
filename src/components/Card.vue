<template>
    <div class="card">
        <div class="image-card">
            <img :src="imageSource">
        </div>
        <p>{{Titulo}}</p>
    </div>
</template>
<script>
export default {
    props:['Titulo','imageSource']
}
</script>
<style>
    *{
        box-sizing: border-box;
    }
    .card{
        width: 240px;
        height: 219px;
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        border-radius: 2px;
        background: #FFFFFF;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
    }
    .card img{
        margin-top: 30px;
        width: 55%;
        height: 70%;
    }
    .image-card{
        width: 100%;
        height: 147px;
        background: #C4C4C4;
    }
    .card p{
        line-height: 24px;
        margin-left: 24px;
    }
</style>