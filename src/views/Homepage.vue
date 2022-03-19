<template>
  <div>
    <!-- Display component as such passing any props you need to-->
    <Collection />
    <Description />
    <HomeSection1 />
    <Pricing />
    <HomeNFTDisplay />
  </div>
</template>

<script>
//Import your components
import HomeSection1 from "@/components/homepage/HomeSection1.vue";
import HomeNFTDisplay from "@/components/homepage/HomeNFTDisplay.vue";
import Description from "@/components/homepage/DescriptionView.vue";
import Collection from "@/components/homepage/Collection.vue";
import Pricing from "@/components/homepage/Pricing.vue";

export default {
  name: "Homepage",
  components: {
    HomeSection1, // Add your components
    HomeNFTDisplay,
    Description,
    Collection,
    Pricing,
  },
};
</script>

<style lang="scss" scoped></style>
