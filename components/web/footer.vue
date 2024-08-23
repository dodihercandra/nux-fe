<template>
    <footer class="footer-top pt-4">
        <b-container>
          <b-row>
            <b-col md="4">
              <h5>TENTANG</h5>
              <hr>
              <p> Pelopor produsen produk-produk FRP pertama di indonesia yang telah berdiri sejak 40 tahun.</p>
            </b-col>
            <b-col md="4">
              <h5>TAGS</h5>
              <hr>
              <div>
                <nuxt-link :to="{name: 'tag-slug', params:{slug: tag.slug}}" class="btn btn-primary-dark btn-sm mb-1 mr-1 shadow-sm" v-for="tag in tags" :key="tag.id">{{ tag.name }}</nuxt-link>
              </div>
            </b-col>
            <b-col md="4">
              <h5>KONTAK</h5>
              <hr>
              <p><i aria-hidden="true" class="fa fa-map-marker"></i> Jl. Pembangunan 2 No 34 Batusari, Batuceper
                Tangerang, Indonesia <br><br><i class="fas fa-phone"></i> +6281-552-5582 </p>
            </b-col>
          </b-row>
        </b-container>
        <b-container fluid class="footer-bottom">
          <b-row class="p-3 justify-content-center">
            <div class="text-white font-weight-bold"> 2016 © Copyrights Orindo Eratec. All Rights Reserved.
            
            </div>
          </b-row>
        </b-container>
      </footer>
  </template>
  
  <script>
  export default {
  
      //data function
      data() {
        return {
          //state tags
          tags: []
        }
      },
  
      async fetch() {
  
        //fething tags on Rest API
        await this.$axios.get('/api/web/tags')
        .then(response => {
  
          //assign response to state "tags"
          this.tags = response.data.data
        })
      }
  
  }
  </script>
  
  <style>
  
  </style>