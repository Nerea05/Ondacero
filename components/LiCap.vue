<template>
    
    <NuxtLink to="/player"> <div class="LiCap">
        <p>{{tituloLiCap}}</p>
        <ul class="box"> 
            <li class="icon-li"><fa :icon="['fas', 'heart']" /></li>
        <li class="icon-li"><fa :icon="['fas', 'arrow-down']" /></li>
         <li class="icon-li"><fa :icon="['fas', 'share-nodes']" /></li>
        </ul>

    </div></NuxtLink>
</template>

<style lang="sass">
.icon-li
    margin-left: 20px
.LiCap
    @apply mt-6
    height: 90px
    font-weight: bold
    &:hover
        background-color: $secundaryGreen
        padding: 10px
        border-top-left-radius: 8px
        border-bottom-left-radius: 8px
.LiCap
    @media only screen and (max-width: 800px)
        width: 330px  

.box 
    display: flex
    position: relative
    right: 20px
    

</style>

<script>
export default {
   name: "LiCap",
   props:['tituloLiCap']
}
</script>