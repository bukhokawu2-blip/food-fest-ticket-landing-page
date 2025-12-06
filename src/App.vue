<template>
  <div class="container">
    <header class="header">
      <h1>Cape Town Food Fest</h1>
      <p>Explore our ticket tiers and find your perfect festival experience.</p>

      <h3>Favourites: {{ favouriteCount }}</h3>
    </header>

    <ticket-list 
      :tickets="tickets" 
      @favourite="increaseFavourite"
    />
  </div>
</template>

<script>
import TicketList from './components/TicketList.vue'

export default {
  name: "App",
  components: {
    TicketList
  },

  data() {
    return {
      favouriteCount: 0,

      tickets: [
        {
          id: 1,
          name: "Bronze Ticket",
          price: 150,
          benefits: ["Access to food stalls", "Live music"],
          featured: false
        },
        {
          id: 2,
          name: "Silver Ticket",
          price: 300,
          benefits: ["All Bronze benefits", "VIP seating", "2 free drinks"],
          featured: true     // ✨ FEATURED
        },
        {
          id: 3,
          name: "Gold Ticket",
          price: 500,
          benefits: ["All Silver benefits", "Meet the chefs", "Backstage pass"],
          featured: false
        }
      ]
    }
  },

  methods: {
    increaseFavourite() {
      this.favouriteCount++
    }
  }
}
</script>

<style>
.container {
  width: 90%;
  margin: auto;
  font-family: Arial, sans-serif;
}
.header {
  text-align: center;
  margin-bottom: 20px;
}
</style>


    
