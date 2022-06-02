<template>
<div>
    <button class="btn1-line"> <p class="button-text-line"> {{text}}</p></button>
    </div>
    
</template>

<script>
export default {
    
}
</script>

<style lang="sass">
.btn1-line
 color: $green 
 border: 3px solid $green 
 @apply h-8 w-28 rounded-3xl text-white font-bold 
 &:hover
      background-color: $green
.btn1-line
    @media only screen and (max-width: 800px)
        @apply h-8 w-20
.button-text-line
    color: $green
    @media only screen and (max-width: 800px)
         font-size: 12pt
.button-text-line
     &:hover
      color: $white


        
 
</style>

<script>
export default {
   name: "Button2Line",
   props:['text']
}
</script>