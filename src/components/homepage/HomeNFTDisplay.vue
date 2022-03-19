<template>
  <!-- We would like you to render 12 NFTs in the desktop full width view, but limit it to 3 NFTs if mobile width (examples in the design)-->
  <!-- Here you will see conditional rendering separating between mobile Nfts and normal. You may use your own logic for displaying the nfts between the mobile view and desktop-->
  <div>
    <div class="nftSection">
      <a
        href="#"
        v-on:click="checkActive('item')"
        :class="{ active: itemActive }"
        >Items</a
      >
      <a
        href="#"
        v-on:click="checkActive('activity')"
        :class="{ active: activityActive }"
        >Activity</a
      >
    </div>

    <div class="nftContent">
      <div v-for="item in nfts" :key="item.id" class="nftImage">
        <div class="manzoor"><img :src="item.image" alt="" /></div>
        <div class="nftContent_data">
          <div class="nftContent_dataInsight">
            <p>Artwork</p>
            <p>by<b> artist name</b></p>
          </div>
          <div class="nftContent_dataInsight">
            <p>20.5Tx</p>
            <p>{{ item.price }}$</p>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="bottom">
    <p>You’ve seen the all collection</p>
    <div class="bottom_handles">
      <button class="bottom_active">Gallery</button>
      <button @click="scrollTop">Got back to top</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home-NFT-Display",
  data() {
    console.log("here nft", this.fakeNFTdata);
    return {
      mobileNFTs: [], // You may use this to display limited NFTs
      activityActive: false,
      itemActive: true,
      fakeNFTdata: [
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
        {
          image: require("../../assets/scenary.png"),
          id: Math.random().toString(16).slice(2),
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT`,
        },
      ],
      nfts: [],
    };
  },
  mounted() {
    this.checkScreen();
  },
  created() {
    window.addEventListener("resize", this.checkScreen); // On window resize: runs the checkScreen method
  },
  methods: {
    checkScreen() {
      // You will have to add to this method if you want the expected results. Or abandon it entirely and make your own
      console.log("screen width change", window.innerWidth);
      this.windowWidth = window.innerWidth;
      if (window.innerWidth <= 600) {
        // do something
        this.nfts = this.fakeNFTdata.slice(0, 3);
      } else if (window.innerWidth > 600) {
        // do something
        this.nfts = this.fakeNFTdata;
      }
    },

    checkActive(value) {
      if (value === "item") {
        this.itemActive = true;
        this.activityActive = false;
      } else {
        this.itemActive = false;
        this.activityActive = true;
      }
    },
    scrollTop() {
      let currentScroll = document.documentElement.scrollTop,
        int = setInterval(frame, 6);

      function frame() {
        if (0 > currentScroll) clearInterval(int);
        else {
          currentScroll = currentScroll - 12;
          document.documentElement.scrollTop = currentScroll;
        }
      }
    },

    getRandomInt(min, max) {
      min = Math.ceil(min);
      max = Math.floor(max);
      return Math.floor(Math.random() * (max - min) + min);
    },
  },
  computed: {
    GenerateNFTData() {
      const NFTs = [];

      for (var i = 0; i < this.images.length; i++) {
        NFTs.push({
          id: Math.random().toString(16).slice(2),
          picture: this.images[i].image,
          artist: "Unknown Artist",
          price: this.getRandomInt(50, 100),
          name: `NFT-${i + 1}`,
        });
      }

      // Generate NFT data and push into the NFT array
      // You can create a loop that loops through n NFTS generating the data with unique IDs
      // Use these generated NFTs to display on the market.
      /** NFT data should look something like:
       * name: 'NFT-1' where 1 is the value of i in your loop
       * artist: 'Unknown Artist'
       * price: 100 #you may keep this random
       * image: this should be any image of your choosing or selected from the shared XD file
       */
      return NFTs;
    },
  },
};
</script>

<style scoped>
.nftContent {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin: 0 5%;
}
.nftSection {
  border-bottom: 1px solid lightgray;
  margin: 1.5rem;
  padding-bottom: 10px;
}
.nftSection > a {
  text-decoration: none;
  margin: 2rem 1rem;
  margin-bottom: 0;
  color: gray;
}

.nftContent_data {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  text-align: left;
  margin: 10px 13%;
  margin-top: -1rem;
}
.nftContent_dataInsight {
  display: flex;
  flex-direction: column;
}
.nftContent_dataInsight > p {
  margin: 0;
}
.nftImage > .manzoor > img {
  width: 100%;
  padding-left: 2px;
}
.nftImage {
  margin: 1rem 1rem;
  background: #efefef;
  border-radius: 25px;
  width: 30%;
}
.bottom > p {
  font-size: 32px;
  color: #000000;
}
.bottom_handles > button {
  width: 130px;
  border-radius: 22px;
  height: 42px;
  border: transparent;
  color: white;
  margin: 0 1rem 5rem 0;
  background: #edf7f7;
  color: #5fbdc1;
}
.active,
.bottom_handles > button .active {
  border-bottom: 2px solid skyblue;
  font-weight: bold;
  color: skyblue !important;
}
.active {
  padding-bottom: 10px;
}
.bottom_handles > button:active,
.bottom_handles > button:visited,
.bottom_handles > button:focus {
  background: #5fbdc1;
  color: white;
}
@media only screen and (max-width: 350px) {
  .nftImage > .manzoor > img {
  }
}
@media only screen and (max-width: 600px) {
  .nftImage {
    width: 75%;
  }
  .nftContent_data {
    font-size: 18px;
  }
  .bottom_handles {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 1rem;
  }
  .bottom_handles > button {
    margin-bottom: 1rem;
  }
}
</style>
