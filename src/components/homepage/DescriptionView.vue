<template>
  <div class="artist">
    <h3>Artist Name</h3>
    <p v-if="!readMore">{{ shortContent.substring(0, 182) }}...</p>
    <p v-if="readMore">{{ shortContent }}</p>
    <p v-if="readMore">{{ fullContent }}</p>
    <p class="readMore" v-if="!readMore" v-on:click="readMore = !readMore">
      Read More
    </p>
    <p class="readMore" v-if="readMore" v-on:click="readMore = !readMore">
      Hiddle
    </p>
  </div>
</template>

<script>
export default {
  name: "Descript-view",
  data() {
    return {
      readMore: false,
      shortContent:
        "Description of the NFT / collectable - Examples such the content of NFTs, specific themes of the collection, quotations by the creator, the meaning behind the creation of this piece etc.",
      fullContent:
        "Description of this collection - - Examples such the content of NFTs, specific themes of the collection, quotations by the creator, the meaning behind the creation of this collection etc Description of this collection - - Examples such the content of NFTs, specific themes of the collection, quotations by the creator, the meaning behind the creation of this collection etcDescription of this collection - - Examples such the content of NFTs, specific themes of the collection, quotations by the creator, the meaning behind the creation of this collection etc",
    };
  },
};
</script>

<style scoped>
.artist {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.artist > p {
  margin: 10px 25%;
}
.readMore {
  color: #50b1b5;
}
</style>
