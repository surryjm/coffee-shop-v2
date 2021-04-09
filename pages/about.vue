<template>

    <div class="about">
      <main id="main-content" class="row justify-content-center mb-5">
        <section class="about-text">
          <h2 class="text-uppercase text-center">About Us</h2>
          <p class="mb-5">With exceptional espresso, pastries baked from scratch, gluten-free options, house-made granola, and delicious panini, Ten Ton Art & Coffee has what you crave. A perfect choice for breakfast, lunch, or a quick pick-me-up.</p>
          <p>Coffee shops in towns and villages throughout the world always seem to be community gathering places, and Ten Ton is no exception. Join us!</p>
        </section>
      
        <section class="col-xl-12 col-lg-8 col-md-10 col-sm-12 text-center mb-5">
          <h3 class="text-uppercase">Instagram</h3> 

          <!-- INSTAGRAM COMPONENT -->
          <InstagramFeed
            v-for="(photo, i) in photos"
            v-on:click.native="toggleBorder(i)" 
            :class="{borderOn: i === activeItem}" 
            v-bind:key="i" 
            :photo="photo"
            class="img-fluid m-2" 
            width="250" 
            height="250"
            />
        </section>

      </main>
    </div>
  
</template>

<script>

import InstagramFeed from "../components/InstagramFeed.vue"; // INSTAGRAM COMPONENT
import axios from 'axios';
import {toggle} from '../mixins/toggle.js'

export default {
name: 'About',
title: 'Ten Ton Coffee - About',
components: {
    InstagramFeed, // INSTAGRAM COMPONENT
  },
mixins: [toggle],
  data () {
      return {
        loading: true,
        photos: null,
        errored: false,
        title: 'Ten Ton Coffee - About',
      }
    },
  head () {
    return {
      title: this.title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: 'Ten Ton Coffee - About'
        }
      ]
    }
  },
  mounted () {
    axios
      .get('https://api.pexels.com/v1/search?per_page=10&orientation=landscape&query=coffee&page=1', {
        headers: {
          Authorization: '563492ad6f917000010000016dcd439c4e5c4595919e4bbaa709f37b'
        }
      })
     .then(response => {
        this.photos = response.data.photos
      })
      .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

.borderOn {
    box-shadow: 0 15px 15px rgba(0,0,0,0.6);
  }

</style>
