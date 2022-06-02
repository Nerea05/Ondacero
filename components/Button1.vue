<template>
<div>
    <button class="btn1"> <p class="button-text">button</p></button>
    </div>
    
</template>

<script>
export default {
    
}
</script>

<style lang="sass">
.btn1 
 @apply w-16 h-10 w-32 rounded-3xl text-white font-bold mt-2
 background-color: $green
 &:hover
      background-color: $blue
 
</style>