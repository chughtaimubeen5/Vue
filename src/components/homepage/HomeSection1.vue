<template>
  <!-- <h2> Welcome to your Technical Test !</h2> -->

  <Collection />

  <Description />

  <Pricing />
</template>

<script>
import Description from "@/components/homepage/DescriptionView.vue";
import Collection from "@/components/homepage/Collection.vue";
import Pricing from "@/components/homepage/Pricing.vue";

export default {
  name: "HomeSection1",
  component: {
    Description,
    Collection,
    Pricing,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.flexColumn {
  display: flex;
  flex-direction: column;
}
.flexRow {
  display: flex;
  flex-direction: row;
}
</style>
