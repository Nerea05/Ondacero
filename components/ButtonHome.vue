<template>
  <button class="btn-home">{{Home}}</button>
  
</template>

<style lang="sass">
.btn-home
    @apply w-10 h-10 rounded-full mt-2
    background-color: $green
    color: $white

    &:hover
        background-color: $blue

</style>

<script>
export default {
   name: "ButtonHome",
   props:['Home']
}
</script>
