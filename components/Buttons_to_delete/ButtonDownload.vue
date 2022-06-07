<template>
  <button class="btn-download"><fa :icon="['fas', 'arrow-down']" /></button>
</template>

<script>
export default {

}
</script>

<style lang="sass">
.btn-download
  width: 30px
  height: 30px
  color: $green
  border: 3px solid $green 
  @apply rounded-full

  &:hover
        color: $blue

</style>