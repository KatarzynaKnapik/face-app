<template>
    <div class="navbar">
        <h2 class="text">Face App</h2>
        <p class="name">Katarzyna Knapik</p>
    </div>
</template>
<script>
export default {
    name: 'Navbar',
    data(){
        return{

        }
    }
}
</script>
<style>
    @import url('https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&display=swap');
    .navbar{
        margin: 0;
        width: 100%;
        position:absolute;
        height: 100px;
        top:0;
        left:0;
        background: linear-gradient(45deg, black, grey);
        display: flex;
        justify-content: space-between
    }
    .navbar .text{
        color: #fff;
        position: relative;
        top: 4px;
        left: 100px;
        font-size: 35px;
        font-family: 'Amatic SC', cursive;
        font-weight: 400;
        letter-spacing: 0.2em;

    }
    .navbar .name{
        color: #000;
        position: relative;
        top: 40px;
        right: 10px;
        font-family: 'Amatic SC', cursive;
        font-weight: 400;
        font-size: 25px;
    }
</style>