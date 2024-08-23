<template>
    <div>
      <!-- navbar -->
      <Navbar />
  
      <!-- content -->
      <Nuxt />
  
      <!-- footer -->
      <Footer />
  
    </div>
  </template>
  <script>
    import Navbar from '@/components/web/navbar.vue'
    import Footer from '@/components/web/footer.vue'
    export default {
      components: {
        Navbar,
        Footer
      },
    }
  </script>
  
  <style>
    body {
      background-color: #ccdcec !important;
    }
  
    .jumbotron {
      background: #186399 !important;
      color: white;
    }
  
    .bg-navbar {
      background: #12466B;
      
    }
   
   .bg-navbar a:hover{
    
    background-color: #1c669b;
    border-radius: 5px;
    width: 100%;
   
 }
   
   .dropdown-menu{
    background-color: #0f456b;
    border:none;
  
   }
   .dropdown-item{
    
    color: white;
   }

    .btn-primary {
      background-color: #1c669b;
      border-color: #1c669b;
    }
  
    .btn-primary:hover {
      background-color: #1c669b;
      border-color: #1c669b;
    }
  
    .btn-primary-dark {
      background-color: #0f456b;
      border-color: #0f456b;
      color: white;
    }
  
    .btn-primary-dark:hover {
      color: white;
    }
  
    .carousel-item .img-fluid {
      border-radius: .5rem;
    }
  
    .card-category {
      background-color: #dadada;
    }
  
    .object-fit-cover {
      object-fit: cover;
    }
  
    .footer-top {
      background-color: #186399;
      color: white;
    }
  
    .footer-bottom {
      background-color: #12466B;
    }
    .col-6 {
      color: #12466B;
     
    }
    .col-12 {
      color: #12466B;
     
    }
   
   .bg-hero[data-v-f12bf83a] {
    background-color: black;
    height: 500px;
    
    background-size: cover;
    position: inherit ;
   }
   .text-justify[data-v-f12bf83a] {
    color: white;
    position: absolute;
    margin-top: 100px;
    margin-left: 20px;
    
   }
  </style>