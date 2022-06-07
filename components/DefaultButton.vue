<template>

    <button class="btn2" v-on:click.prevent > 
        <fa 
            v-if="iconType"
            :icon="['fas', iconType]" />
        <p 
            v-if="textbutton2" 
            class="button-text">
            {{textbutton2}}
        </p>
    </button>
    
    
</template>

<script>
export default {
   name: "button2",
   props:['textbutton2', 'iconType']
}
</script>

<style lang="sass">
.btn2 
    @apply h-10 px-3 py-2 rounded-3xl text-white font-bold 
    background-color: $green
    display: block
    margin-right: 5px
    &:hover
        background-color: $blue
.btn2
    @media only screen and (max-width: 800px)
        @apply h-8 w-20
.button-text
     @media only screen and (max-width: 800px)
         font-size: 12pt

        
 
</style>