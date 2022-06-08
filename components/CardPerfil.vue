<template>
  <div class="card-perfil">
      <img class="img-podcast" src="/podcast1.png" alt="emoji">
     <div class="card-perfil-text">
         <h5 >Título</h5>
     <h6 id= "sub-text" class="body2"><span class="autor">autor</span></h6>
     <div class="social">
         <default-button class="bt1" :textbutton2="'seguir'" />
     <default-button class="bt2" :iconType="'arrow-down'" />
     <default-button class="bt2" :iconType="'share-nodes'" />
     </div>

     </div>
  </div>
</template>

<script>
export default {
   
   
}
</script>

<style lang="sass">

.social
    display: flex
    position: relative
    right: 4px
    @media only screen and (max-width: 800px)
     .bt2
         display: none
        
.card-perfil
    background-color: $white
    @apply w-80 ml-12 mt-16
    border-radius: 150px
    height: 480px
    box-shadow: $shadow-left-green
    @media only screen and (max-width: 800px)
        @apply w-60  ml-6
        height: 240px
        display: flex
        flex-direction: row

.card-perfil-text
   position: relative
   top: 60px
   left: 60px
.img-podcast
    width: 250px
    position: relative
    top: 35px
    left: 35px
    @media only screen and (max-width: 800px)
        left: 10px
        width: 230px
        height: 150px

</style>