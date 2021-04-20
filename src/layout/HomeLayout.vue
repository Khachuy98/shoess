<template>
<div class="topnav">
  <b-navbar class="topnavbar" toggleable="lg" type="dark">
    <b-navbar-brand href="#">Shoes Store</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#">Home</b-nav-item>
        <b-nav-item href="#">Shop</b-nav-item>
        <b-nav-item href="#" >About</b-nav-item>
        <b-nav-item href="#" >Contact</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
              <b-col lg="6" class="my-1">
        <b-form-group
          label-for="filter-input"
          label-cols-sm="12"
          label-align-sm="right"
          label-size="sm"
          class="mb-0"
        >
          <b-input-group size="sm" class="search">
            <b-form-input
              id="filter-input"
              v-model="filter"
              type="search"
              placeholder="Type to Search"
            ></b-form-input>

            <b-input-group-append>
              <b-button :disabled="!filter" @click="filter = ''">Clear</b-button>
            </b-input-group-append>
          </b-input-group>
        </b-form-group>
      </b-col>
        <b-nav-item-dropdown text="Lang" right>
          <b-dropdown-item href="#">En</b-dropdown-item>
          <b-dropdown-item href="#">Vi</b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item-dropdown text="User" right>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
      <div class="main-panel">
        
      <top-navbar></top-navbar>

      <dashboard-content @click="toggleSidebar">

      </dashboard-content>

      <content-footer></content-footer>
    </div>
</div>

</template>

<script>
  import HeaderContent from './HeaderContent.vue'
  import ContentFooter from './ContentFooter.vue'
  import MobileMenu from './MobileMenu.vue'
export default {
  components: {
    HeaderContent,
    ContentFooter,
    MobileMenu,
  },
  methods: {
        toggleSidebar () {
        if (this.$sidebar.showSidebar) {
        this.$sidebar.displaySidebar(false)
        }
      }
  }
}
</script>

<style scoped>
  .search{
    margin: 30px 7px;
  }
    .topnav{
        background-color: rgb(164, 166, 168);
    }
    .mr-sm-2{
        border-radius: 12px;
    }
    .main-panel{
    background: #00000000;
    position: relative;
    float: right;
    width: calc(100% );
    min-height: 100%;
    }
</style>