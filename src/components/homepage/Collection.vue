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
  height: 142px;
  width: 100%;
  background-image: url("../../assets/pexels-photo-1183992@2x.png");
  object-fit: cover;
  z-index: -1;
  background-size: 100% 100%;
}

.avatar {
  margin-top: -1.5rem;
  height: 94px;
  width: 94px;
}
.collection_title {
  padding-top: 1rem;
  font-size: 38px;
  color: white;
  position: absolute;
  left: 0;
  right: 0;
  opacity: 1 !important;
  font-weight: 300;
}
.collection_image {
  position: absolute;
  top: 0;
  height: 142px;
  width: 100%;
  background: transparent linear-gradient(180deg, #000000d6 0%, #00000026 100%)
    0% 0% no-repeat padding-box;
  opacity: 1;
}

@media only screen and (max-width: 750px) {
  .collection_title {
    font-size: 32px;
  }
  .collection {
    height: 210px;
  }
  .collection_image {
    height: 210px;
  }
  .avatar {
    margin-top: -4.5rem;
    height: 150px;
    width: 150px;
  }
  .collection_title {
    padding-top: 0;
    font-size: 44px;
    font-weight: 300;
  }
}
@media only screen and (max-width: 450px) {
  .collection_title {
    font-size: 34px;
  }
}
</style>
