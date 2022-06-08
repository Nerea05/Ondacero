<template>
 <div class="body">
      <div class="playerbox">
      <div >
      <div class="p-imagebox"><img class="podcastimage" src="/podcast1.png" alt=""></div>
  </div>
    <div class="podcast-info" >
         <h5 >After Hours</h5>
     <h6  class="body2"><span class="autor">Gema Ruiz. Gasolina, coches de choque y la 'Adele de feria'
</span></h6>
 <p class="info">Cuarto episodio de 'After hours', con Gemma Ruiz e Isa Blanco. ¿Qué tienen en común Adele y los coches de choque? ¿Sabes echar gasolina como un profesional o eres tan desastre como nosotras? ¡Escucha, escucha, que hoy hay temazos! </p> </div>
   <audio-player />
</div>
 </div>



</template>



<style lang="sass">
.body
    background-color: $green
    @media only screen and (max-width: 800px)
        background-color: $white

.podcastimage
    width: 500px
    padding: 40px
    @media only screen and (max-width: 800px)
         width: 450px
         position: relative
         left: 20px
         background-color: $white
         @apply rounded-full
         box-shadow: 0px -15px 15px -3px rgba(0,0,0,0.1)

.podcast-info
    width: 800px
    position: relative
    left: 500px
    bottom: 250px
    @media only screen and (max-width: 800px)
        left: 70px
        width: 300px
        bottom: 0px
        top: 200px



.info
        font-size: 20px
        margin-top: 25px
        @media only screen and (max-width: 800px)
             font-size: 10px


.playerbox
    background-color: $white
    box-shadow: 0px -15px 15px -3px rgba(0,0,0,0.1)
    position: relative 
    top: 100px
    height: 600px
    border-top-left-radius: 10%
    border-top-right-radius: 10%
    @media only screen and (max-width: 800px)
        box-shadow: none


</style>
