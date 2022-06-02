<template>
    <div class="list-box">
        <div class="box-encabezado">
        <h3>titulo</h3>
        <h6 >autor</h6>
        <ul>
            <liCap tituloLiCap= " 1x4: Gasolina, coches de choque y la 'Adele de feria'" />
            <liCap tituloLiCap= " 1x5: ¿Es corazón o melocotón?, Peta Zetas, Push Pop y otras chuches"/>
            <liCap tituloLiCap= " 1x6: Tú aguanta viendo la serie 20 años, que luego remonta" />
            <liCap />
        </ul>
        </div>
    </div>
</template>

<style lang="sass">
.list-box
    background-color: $white
    border-top-left-radius: 10%
    border-bottom-left-radius: 10%
    width: 1000px
    height: 600px
    @apply  ml-36 mt-16
    box-shadow: $shadow-right-green
    @media only screen and (max-width: 800px)
        @apply ml-10
        width: 400px
        border-radius: 10%

.box-encabezado
    @apply ml-28 mt-6
    @media only screen and (max-width: 800px)
        @apply ml-10 mt-6




</style>