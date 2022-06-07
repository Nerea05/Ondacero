<template>
<button class="btn-user"><fa :icon="['fas', 'user']" /></button>
</template>

<style lang="sass">
.btn-user
    @apply w-10 h-10 rounded-full mt-2
    background-color: $green
    color: $white

    &:hover
        background-color: $blue

</style>