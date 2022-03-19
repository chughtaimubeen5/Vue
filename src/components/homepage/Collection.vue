<template>
  <div class="collection" id="collection">
    <div class="collection_image" />
    <p class="collection_title flexColumn">Collection Name</p>
  </div>
  <img src="../../assets/avatar.png" alt="" class="avatar" />
</template>

<script>
export default {
  name: "Collection",
};
</script>

<style scoped>
.collection {
  position: relative;
  height: 190px;
  width: 100%;
  background-image: url("../../assets/pexels-photo-1183992@2x.png");
  object-fit: cover;
  z-index: -1;
}

.avatar {
  margin-top: -3rem;
}
.collection_title {
  padding-top: 1rem;
  font-size: 38px;
  color: white;
  position: absolute;
  left: 0;
  right: 0;
  opacity: 1 !important;
}
.collection_image {
  position: absolute;
  top: 0;
  height: 190px;
  width: 100%;
  background: transparent linear-gradient(180deg, #000000 0%, #0000003c 100%) 0%
    0% no-repeat padding-box;
  opacity: 0.3;
}

@media only screen and (max-width: 750px) {
  .collection_title {
    font-size: 32px;
  }
}
</style>
