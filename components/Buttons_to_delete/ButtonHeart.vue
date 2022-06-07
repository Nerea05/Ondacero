<template>
  <button class="btn-heart"><fa :icon="['fas', 'heart']" /></button>
</template>

<style lang="sass">
.btn-heart
    @apply w-10 h-10 rounded-full mt-2
    background-color: $green
    color: $white

    &:hover
        background-color: $blue

</style>