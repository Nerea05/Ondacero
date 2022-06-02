<template>
<div>
    <button class="btn1" v-on:click.prevent > <p class="button-text">button</p>
    </button>
    </div>
    
</template>

<script>
export default {
    
}
</script>

<style lang="sass">
.btn1 
 @apply h-10 w-40 rounded-3xl text-white font-bold 
 background-color: $green
 &:hover
      background-color: $blue
.btn1 
    @media only screen and (max-width: 800px)
        @apply h-8 w-20
.button-text
     @media only screen and (max-width: 800px)
         font-size: 12pt

        
 
</style>