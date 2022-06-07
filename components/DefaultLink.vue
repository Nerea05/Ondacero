<template>

    <NuxtLink :to="ruta" 
        class="btn2"> 
        <fa 
            v-if="iconType"
            :icon="['fas', iconType]" />
        <p 
            v-if="textbutton2" 
            class="button-text">
            {{textbutton2}}
        </p>
    </NuxtLink>
    
    
</template>

<script>
export default {
   name: "DefaultLink",
   props:['textbutton2', 'iconType', 'ruta']
}
</script>

