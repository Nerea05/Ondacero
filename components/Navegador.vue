<template>
  <nav>
    <ul>
      <li class="logo-icon">
        <img class="logo" src="logo.svg" alt="logo-de-ondacero" />
      </li>
      
        <li>
            <default-link :iconType="'home'" :ruta="'/'" />
        </li>
     
      <li>
          <default-link :iconType="'heart'" :ruta="'/podcast'" />
      </li>
      <li class="btn">
          <default-link :textbutton2="'mis seguidos'" :ruta="'/podcast'" />
      </li>
      <li><search-bar /></li>
      <li class="btn">
          <default-link :iconType="'user'" :ruta="'/podcast'"/>
      </li>
    </ul>
  </nav>
</template>
<style lang="sass">
nav
    @apply p-4
    @media only screen and (max-width: 800px)
        @apply ml-2 mt-2

    ul
        display: flex
        flex-direction: row

        li
        @apply  ml-3.5

        .logo
            width: 5em
            @apply mr-96
            @media only screen and (max-width: 800px)
                width: 8em

.btn-home
    @media only screen and (max-width: 800px)
        display: none
.btn-heart
    @media only screen and (max-width: 800px)
        display: none
.btn
    @media only screen and (max-width: 800px)
        display: none
</style>