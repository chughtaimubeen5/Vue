<!-- You may notice this navbar is not responsive-->
<!-- We would like you to style it so it is responsive-->
<!-- You do not need to make the dropdown menu on the "Featured Collections" -->
<template>
  <div>
    <div v-if="!isnavbarOpen">
      <div class="navbar_container">
        <img
          class="nav_banner"
          src="https://res.cloudinary.com/risidio/image/upload/v1633609222/RisidioMarketplace/gradienta-m_-1_v4hs5p.svg"
          alt=""
        />
      </div>
      <div class="mainNavbar">
        <ul>
          <img :src="logo" alt="risidio-logo" />
          <li class="nav-item">Gallery</li>
          <li class="nav-item">
            Featured Collections<img
              src="../../assets/caretDown.svg"
              alt=""
              class="caret_down"
            />
          </li>
          <li class="nav-item right">How It Works</li>
          <li class="nav-item">about Risidio</li>
          <li class="nav-item covered">My NFTs</li>
          <div class="mobile_nav" @click="openNavbar">
            <img src="../../assets/Menu_icon.svg" alt="" class="burger_icon" />
            <div class="openNavbar" v-if="isnavbarOpen">
              <div class="navbar_container">
                <img
                  class="nav_banner"
                  src="https://res.cloudinary.com/risidio/image/upload/v1633609222/RisidioMarketplace/gradienta-m_-1_v4hs5p.svg"
                  alt=""
                />
              </div>
            </div>
          </div>
        </ul>
      </div>
    </div>

    <div v-if="isnavbarOpen">
      <div class="navbar_container navbar_containerBack"></div>
      <div class="mainNavbar mainNavbarback">
        <ul style="margin: 0">
          <img :src="logo" alt="risidio-logo" />
          <li style="color: white" @click="openNavbar">X</li>
        </ul>
        <div class="mobileNavbar_topOptions">
          <a href="#" disabled class="mobileNavbar_topOptions_dark">Gallery</a>
          <a href="#" disabled class="mobileNavbar_topOptions_dask"
            >Collection</a
          >
          <br />
          <hr style="border-bottom: 1px; width: 100%" />
          <a href="#" class="mobileNavbar_topOptions_light">how it works</a>
          <a href="#" class="mobileNavbar_topOptions_light">About Risidio</a>

          <br />
          <button>Register with Hiro wallet</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      logo: "https://res.cloudinary.com/risidio/image/upload/v1633609248/RisidioMarketplace/Group_-1_fgpanq.svg",
      isnavbarOpen: false,
    };
  },
  methods: {
    openNavbar() {
      this.isnavbarOpen = !this.isnavbarOpen;
      console.log("navbar open", this.isnavbarOpen);
    },
  },
};
</script>

<style scoped>
.mainNavbar {
  margin: 0 50px 50px 50px;
  margin: 0;
}
.mainNavbar ul {
  display: flex;
  flex-direction: row;
  text-decoration: none;
  align-items: center;
}
.mobile_nav {
  display: none;
}
.covered {
  background: #423d95;
  color: #5fbdc1 !important;
  font-weight: bold;
  border-radius: 16px;
  width: 120px;
  padding: 0.5rem;
}

@media only screen and (max-width: 750px) {
  .covered {
    width: 100px;
    padding: 0.3rem;
    border-radius: 12px;
  }
}

@media only screen and (max-width: 900px) {
  .nav-item {
    display: none;
  }
  .mobile_nav {
    display: grid;
    flex: right;
  }
  .openNavbar {
    display: flex;
    flex-direction: column;
    position: relative;
    top: 0;
    width: 100%;
    left: 0;
  }
}
.caret_down {
  margin-left: 1rem;
}
.navbar_containerBack {
  background-image: url("../../assets/Rectangle.svg");
}
.mobileNavbar_topOptions {
  background: #182564;
  display: flex;
  flex-direction: column;
  text-align: left;
}
.mobileNavbar_topOptions > button {
  background: #493d93;
  border-radius: 18px;
  width: 90%;
  margin: 0 auto;
  color: #5db0bb;
  height: 45px;
  border: none;
  margin-bottom: 2rem;
  font-weight: bold;
  margin-top: 1rem;
}

.mobileNavbar_topOptions > a {
  text-decoration: none;
  margin-top: 1rem;
  color: white;
  padding-left: 2rem;
}
.mobileNavbar_topOptions_dark {
  font-weight: bold;
  font-size: 18px;
}
.mobileNavbar_topOptions_light {
  font-weight: lighter;
}
.mainNavbarback {
  background: #182564;
}
.mainNavbarback > ul > li {
  list-style: none;
  font-size: 30px;
  font-weight: bold;
  float: right;
  position: absolute;
  top: 2rem;
  right: 2rem;
}
.burger_icon {
  position: absolute;
  right: 2rem;
  top: 2rem;
}
.risidio-logo {
  align-self: flex-start;
}
.nav-item {
  list-style-type: none;
  margin: 0 20px;
  color: white;
  font-size: 12px;
  line-height: 15px;
  cursor: pointer;
}
.right {
  margin-left: auto;
}
.nav_banner {
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100px;
  object-fit: cover;
  z-index: -11;
}
</style>
