<template>
  <div id="app">
    <nav class="navbar has-shadow" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a class="navbar-item">MyCompany</a>

        <div class="navbar-burger" v-on:click="toggleNav" v-bind:class="{ 'is-active': isActive }"> 
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>

      <div class="navbar-menu" v-bind:class="{ 'is-active': isActive }">
        <div class="navbar-end" >
          <router-link to="/" class="navbar-item r-item">Home</router-link>
          <router-link to="faq" class="navbar-item r-item">Features</router-link>
          <router-link to="faq" class="navbar-item r-item">About</router-link>
          <router-link to="faq" class="navbar-item r-item">FAQ</router-link>

          <div class="navbar-item">
            <p class="control">
              <a href="" class="button is-primary is-outlined">
                <span class="icon">
                  <i class="fa fa-download"></i>
                </span>
                <span>Join Now</span>
              </a>
            </p>
          </div>
        </div>
      </div>
    </nav>

    <router-view/>

    <footer class="footer is-primary">
      <div class="container">
        <div class="columns">
          <div class="column">
            <p>And this right here is a spiffy footer, where you can put stuff.</p>
          </div>
          <div class="column has-text-right">
            <a href="#" class="icon"><i class="fa fa-facebook"></i></a>
            <a href="#" class="icon"><i class="fa fa-twitter"></i></a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: function() {
    return {
      isActive: false
    }
  },
  methods: {
    toggleNav: function() {
      this.isActive = !this.isActive;
    }
  }
}
</script>

<style lang="sass">
@import '../node_modules/bulma/bulma.sass'
@import '../node_modules/font-awesome/css/font-awesome.min.css'
@import 'mq'

.navbar
  background-color: #383838
  a:hover
    color: gray

.navbar-brand a 
  color: #fff
  font-weight: bold

a.r-item  
  color: #C1C1C1
  padding: 0.5rem 1.75rem
  +mobile
    color: gray
    &:hover
      background-color: #F1F1F1

.navbar-burger 
  &:hover
    background-color: #F1F1F1
  span
    background-color: #C1C1C1
    color: #C1C1C1
    &:hover
      background-color: #F1F1F1

footer
  background-color: $primary !important
  color: #fff

  .icon
    color: #fff
    margin-left: 20px
</style>