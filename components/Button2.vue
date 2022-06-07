<template>
<div>
    <button class="btn2" v-on:click.prevent > <p class="button-text">{{textbutton2}}</p>
    </button>
    </div>
    
</template>

<script>
export default {
   name: "button2",
   props:['textbutton2']
}
</script>

<style lang="sass">
.btn2 
 @apply h-10 w-40 rounded-3xl text-white font-bold 
 background-color: $green
 &:hover
      background-color: $blue
.btn2
    @media only screen and (max-width: 800px)
        @apply h-8 w-20
.button-text
     @media only screen and (max-width: 800px)
         font-size: 12pt

        
 
</style>