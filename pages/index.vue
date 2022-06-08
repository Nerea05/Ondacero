<template>
  <div>
     <h5  id="section-name" class="h5-pc-bold" >{{tit1}}</h5>
    <card-principal :source="'/presentador1.png'" />
    <h5 id="section-name" class="h5-pc-bold" > {{tit2}} </h5>
    <div class="grid-cards">
    <simple-card :source="'/presentador1.png'"  />
    <simple-card :source="'/presentador2.png'" />
    <simple-card :source="'/presentador3.png'"/>
    <simple-card :source="'/presentador4.png'"/>
    </div>
    <h5 id="section-name" class="h5-pc-bold" > {{tit3}} </h5>
    <div class="grid-cards">
    <simple-card :source="'/podcast1.png'" />
    <simple-card :source="'/podcast2.png'" />
    <simple-card :source="'/podcast2.png'" />
    <simple-card :source="'/podcast1.png'"  />
    </div>

    
  </div>

</template>

<style lang="sass">
.grid-cards
  display: flex
  flex-wrap: wrap
  @apply w-4/5
</style>



<script>
export default {
  name: 'IndexPage',
  layout: 'default.vue',
  data(){
    return{
      tit1: 'Destacados',
      tit2: 'Cultura y humor',
      tit3: 'Deportes',
      tit4: 'Economía',
      tit5: 'Innovación',
      tit6: 'Sociedad',
      
    }
  }
 
}
</script>
