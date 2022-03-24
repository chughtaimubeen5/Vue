<template>
  <div class="data_header flexRow">
    <div class="flexColumn data_header_content" style="border-radius: 25px">
      <div class="data_header_item border">
        <p>Floor Price</p>
        <h5>2,835 STX</h5>
      </div>
      <div class="data_header_item border">
        <p>Owners</p>
        <h5>1,236</h5>
      </div>
      <div class="data_header_item">
        <p>Items</p>
        <h5>2,500</h5>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Pricing",
};
</script>

<style scoped>
.data_header {
  justify-content: center;
}
.border {
  border-right: 1px solid lightgray;
  margin: 0.5rem 0;
}
.data_header_item {
  padding: 0rem 1.5rem;
  width: 33.33%;
  height: 72px;
}
.data_header_content {
  display: flex;
  flex-direction: row;
  width: 50%;
  background: #f9f9f9;
  border-radius: 25px;
  margin: 2rem 0;
  height: 93px;
}
@media only screen and (max-width: 880px) {
  .data_header_content {
    height: 100px;
  }
  .data_header_item {
    padding: 0;
  }
}
@media only screen and (max-width: 750px) {
  .data_header_content {
    width: 50%;
    height: auto;
    width: 260px;
  }
  .border {
    border: 0;
    border-bottom: 1px solid lightgray;
    margin: 0 1rem;
  }
  .data_header_item {
    padding: 1rem 2.5rem;
    margin: 0 auto;
  }

  .data_header_content {
    flex-direction: column;
  }
}
</style>
