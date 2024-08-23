<template>
  <div>
    <b-jumbotron class="p-1 rounded-0 mb-0">
      <b-container>
        <b-row class="mt-1">
          <b-col md="1" class="text-center">
            <b-img src="/images/orindo.png" rounded="square" width="60" heigh ="60"></b-img>
          </b-col>
          <b-col md="11">
            <h3 class="font-weight-bold">Orindo Eratec</h3>
            <p>Integrated Solution For Your Needs</p>
          </b-col>
        </b-row> 
      </b-container>
    </b-jumbotron> 
    <b-navbar toggleable="lg" type="dark" class="bg-navbar">
      <b-container>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          PRODUCT
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="/category/o-line">O-Line</a>
          <a class="dropdown-item" href="/category/o-max">O-Max</a>
          <a class="dropdown-item" href="/category/hi-grid">Hi-Grid</a>
        </div>
      </li>
            <b-nav-item v-for="menu in menus" :key="menu.id" :to="menu.url">{{ menu.name.toUpperCase() }}</b-nav-item>
            <div class="animation start-home"></div>
          
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-form-input v-model="search" @keypress.enter="searchData" size="sm" class="mr-sm-2 border-0" placeholder="tulis kata kunci...">
            </b-form-input>
            <b-button @click="searchData" size="sm" class="my-2 my-sm-0" variant="primary">CARI</b-button>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
  </div>
</template>

<script>
  export default {

    //data function
    data() {
      return {
        //state menus
        menus: [],

        //state search
        search:''
      }
    },

    async fetch() {

      //fething menus on Rest API
      await this.$axios.get('/api/web/menus')
        .then(response => {

          //assign response to state "menus"
          this.menus = response.data.data
        })
    },

    methods:{
      searchData(){
        this.$router.push({
          name: 'search',
          query:{
            q:this.search
          }
        });
      }
    }

  }
</script>

<style>

</style>