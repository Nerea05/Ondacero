<template>
    <div class="LiCap">
        <p>{{tituloLiCap}}</p>

    </div>
</template>

<style lang="sass">
.LiCap
    @apply mt-6
    height: 70px
    font-weight: bold
    &:hover
        background-color: $secundaryGreen
        padding: 10px
        border-top-left-radius: 8px
        border-bottom-left-radius: 8px
.LiCap
    @media only screen and (max-width: 800px)
        width: 330px  

    
</style>

<script>
export default {
   name: "LiCap",
   props:['tituloLiCap']
}
</script>