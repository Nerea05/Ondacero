<template>
<button class="btn-seguir"><fa :icon="['fas', 'user-plus']" /></button>
</template>

<style lang="sass">
.btn-seguir
    @apply w-10 h-10 rounded-full 
    color: $green
    border: 4px 
    border-color: $green
    cursor: pointer

    &:hover
        background-color: $green
        color: $white

</style>