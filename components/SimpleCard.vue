<template>
  <NuxtLink to="/podcast">
  <div>
        <div class="simple-card"> 
        <img class="imgPresentador-simple" :src="source" alt="">
        <div id="text-box-simple">
        <h5 class="leading">Título</h5>
        <h6 id= "sub-text" class="body2"><span class="autor">autor</span></h6>
        </div>
        <span class="btn-follow"><button-seguir /></span>
    </div>


    </div>
  </NuxtLink>
</template>

<script>
export default {
   props:['source']
}
</script>

<style lang="sass">
#section-name
  color: $green
  margin-top: 50px
  margin-left: 50px
  @media only screen and (max-width: 800px)
      margin-left: 30px
.simple-card
    display: flex
    flex-direction: row
    background-color: $white
    @apply mt-9 ml-4 mr-14 
    padding: 5px
    width: 480px
    height: 130px
    border-radius: 200px
    box-shadow: $shadow-right-green
    z-index: 2
    cursor: pointer
    @media only screen and (max-width: 800px)
        @apply mt-6 ml-4 h-32 
        width: 401px
.simple-card
    &:hover
        background-color: $secundaryGreen
.imgPresentador-simple
    margin-left: 60px
    margin-right: 20px
    @apply p-2 pt-4
    @media only screen and (max-width: 800px)
      margin-left: 10px
.text-box-simple
    @media only screen and (max-width: 800px)
      margin-left: 30px
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

.btn-follow
    position: relative
    top: 40px
    left: 65px
    @media only screen and (max-width: 800px)
        left: 40px

</style>


