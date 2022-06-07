<template>
    <NuxtLink to="/podcast">
    <div>
        <div class="card-principal"> 
        <img class="imgPresentador" :src="source" alt="">
        <div id="text-box">
        <h6 id="seccion-text" class= "body">Texto cihdcqnewc</h6>
        <h3 class="leading">Título</h3>
        <h6 id= "sub-text" class="body2"><span class="autor">autor</span> <span class="subtitle3">nombre del programa</span></h6>
        <button-2 textbutton2= "seguir" />
        </div>
    </div>


    </div>
     </NuxtLink>
</template>

<style lang="sass">


#section-name
  color: $green
  margin-top: 50px
  margin-left: 50px
  @media only screen and (max-width: 800px)
      margin-left: 30px
.card-principal
    display: flex
    flex-direction: row
    background-color: $white
    @apply mt-6
    width: 1150px
    height: 340px
    border-top-right-radius: 200px 200px
    border-bottom-right-radius: 200px 200px
    box-shadow: $shadow-right-green
    z-index: 2
    cursor: pointer
    @media only screen and (max-width: 800px)
        @apply h-52 w-11/12
.card-principal
    &:hover
        background-color: $secundaryGreen
.imgPresentador
    margin-left: 150px
    @media only screen and (max-width: 800px)
      margin-left: 10px
#text-box
    margin-left: 100px
    margin-top: 70px
    @media only screen and (max-width: 800px)
      margin-left: 10px
      margin-top: 50px


.leading
    color: $blue
    @media only screen and (max-width: 800px)
        font-size: 30pt
        @apply font-black
#seccion-text
    color: $green
    @media only screen and (max-width: 800px)
        display: none

#sub-text
    color: $green
.autor
     @media only screen and (max-width: 800px)
        @apply font-black




</style>

<script>
export default {
   props:['source']
}

</script>