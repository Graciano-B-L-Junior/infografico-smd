<template>
    <div class="card">
        <div class="image-card"></div>
        <p>{{Titulo}}</p>
    </div>
</template>
<script>
export default {
    props:['Titulo']
}
</script>
<style>
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