<template>
  <div class="home" >
    <div class="d-flex">
      <div class="col-12 col-sm-12">
        <Card 
          typeCard="main" 
          image="Lagoa" 
          topText="front-end" 
          :sub="allSubs" 
          cardTitle="valtech"/>
      </div>
    </div>
    <div class="d-flex">
      <div class="col-sm-12 col-6">
        <Card 
          typeCard="dynamic" 
          image="Venice" 
          topText="Italy" 
          :sub="allSubs" 
          cardTitle="Venice"/>
      </div>
      <div class="col-sm-12 col-3">
        <Card 
          typeCard="dynamic" 
          image="Berlin" 
          topText="germany" 
          :sub="allSubs" 
          cardTitle="Berlin"/>
      </div>
      <div class="col-sm-12 col-3">
        <Card 
          typeCard="dynamic" 
          image="Barcelona" 
          topText="spain" 
          :sub="allSubs" 
          cardTitle="Barcelona"/>
      </div>
    </div>
    <div class="d-flex">
      <div class="col-sm-12 col-3">
        <Card 
          typeCard="dynamic" 
          image="Paris" 
          topText="france" 
          :sub="allSubs" 
          cardTitle="Paris"/>
      </div>
      <div class="col-sm-12 col-3">
        <Card 
          typeCard="dynamic" 
          image="Amsterdam" 
          topText="netherlands" 
          :sub="allSubs" 
          cardTitle="amsterdam"/>
      </div>
      <div class="col-sm-12 col-6">
        <Card 
          typeCard="dynamic" 
          image="London" 
          topText="united kingdom" 
          :sub="allSubs" 
          cardTitle="london"/>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from "@/components/Card.vue";

export default {
  name: "home",
  components: {
    Card
  },
  data: () => ({
    allSubs: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry'
  })
};
</script>
<style lang="scss" scoped>
 .home {
    margin: 3% 10%;
  }
@media screen and (max-width: 500px) {
 .home {
    margin: 3% 8%;
  }
}
</style>
