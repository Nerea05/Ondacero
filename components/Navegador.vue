<template>
    <nav>
        <ul>
            <li class="logo-icon"> <img class="logo" src="logo.svg" alt="logo-de-ondacero"></li>
            <NuxtLink to="/"> <li class="btn-home"> <button-home Home=:) /> </li></NuxtLink>
            <li class="btn-heart"><button-heart /></li>
            <li class="btn"><button-2 /></li>
            <li ><search-bar /></li>
            <li class="btn"><button-user /></li>
            
        </ul>
    </nav>
</template>
<style lang="sass">
nav
    @apply ml-8 mt-2
    @media only screen and (max-width: 800px)
        @apply ml-2 mt-2


    ul
        display: flex
        flex-direction: row

        li
          @apply  ml-3.5
              
          .logo
             width: 8em
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