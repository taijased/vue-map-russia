<template>
    <path 
        :index='index'
        :d='region.path' 
        class='state'  
        @mouseover='isActive = true' 
        @mouseout='isActive = false'
        @click="showTitleDialog(region)"
        :class='{ regionActive: isActive}'/>
</template>

<script>
export default {
  props: {
    region: Object,
    index: Number
  },
  data() {
    return {
      isActive: false
    };
  },
  methods: {
    showTitleDialog (region) {
        console.log(region);
      this.$modal.show('dialog', {
        title: region.fed_okrug  + '<br/><br/>' + region.name,
        text: 'Городское население: ' + region.city_population + ' человек <br/>' + 
             'Сельское население: ' + region.country_population + ' человек <br/>' + 
             'Естественный прирост населения: ' + region.country_natural_increase + ' человек <br/>' + 
             'Среднаяя заработная плата: ' + region.average_nominal_wage + ' рублей <br/>' + 
             'Средние потребительские цены: ' + region.average_consumer_rate + ' рублей <br/>'
      })
    },
  }
};
</script>

<style>
</style>
