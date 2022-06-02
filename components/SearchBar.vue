<template>
   <form >
       <input id="search" type="text" >
       <button class="btn-search"><fa :icon="['fas', 'magnifying-glass']" /></button>
   </form>
   
   
</template>
<style lang="sass">
.btn-search
    @apply w-10 h-10 rounded-full 
    background-color: $green
    color: $white
    position: relative 
    right: 40px
    @media only screen and (max-width: 800px)
        @apply  mt-4
    &:hover
        background-color: $blue
    

#search
    @apply h-10 border-4 rounded-3xl   mt-2
    border-color: $green
    width: 260px
    @media only screen and (max-width: 800px)
         display: none 
</style>