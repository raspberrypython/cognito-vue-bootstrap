<template>
  <b-container>
    <div class="b-main-content">
      <h2>Account Page</h2>
      <h6>Account: {{ user.username }}</h6>
      <p>
        <b-button 
          variant="outline-dark" 
          to="/signOut">Sign Out</b-button>
      </p> 
    </div>
  </b-container> 
</template>

<script>
import { mapState } from 'vuex'

export default {
    computed: {
        ...mapState({
            user: state => state.auth.user,
        })
    }
}
</script>

