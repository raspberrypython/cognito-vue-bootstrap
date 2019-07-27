<template>
  <div>
    <div class="b-title-content">
      <img
        class="title"
        src="@/assets/img/title.png">
    </div>
    <div class="b-login-content">
      <p>
        <b-button 
          v-if="!isAuthenticated" 
          variant="outline-dark" 
          to="/signUp">Sign Up</b-button>
        <b-button 
          v-if="!isAuthenticated" 
          variant="outline-dark" 
          to="/signIn">Sign In</b-button>
        <b-button 
          v-if="isAuthenticated" 
          variant="outline-dark" 
          to="/dashboard">My Dashboard</b-button>
      </p> 
    </div>
    <div class="b-intro-content">
      <img
        class="intro"
        src="@/assets/img/intro.png">
    </div>
    <div class="b-product-content">
      <img
        class="product"
        src="@/assets/img/product.png">
    </div>
    <div class="b-about-content">
      <img
        class="about"
        src="@/assets/img/about.png">
    </div>
    <div class="b-contact-content">
      <img
        class="contact"
        src="@/assets/img/contact.png">
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
    name: 'Navbar',
    computed: {
        ...mapState({
            user: state => state.auth.user,
            isAuthenticated: state => state.auth.isAuthenticated,
        })
    },
    methods: {
        signIn() {
            this.$store.dispatch('signIn')
        }
    }
}
</script>

<style scoped>
img.title, img.intro, img.product, img.about, img.contact {
  width: 100%;
  height: auto;
}

div.b-login-content {
  height: 100px;
}

div.b-login-content p {
  text-align:center;
}

div.b-login-content p a{
  margin-right: 2.5em;
  margin-left: 2.5em;
}
</style>
