<template>
  <div class="card" :class="{ featured: featured }">

    <h2>{{ name }}</h2>
    <h3>R{{ price }}</h3>

    <ul>
      <li v-for="(b, i) in benefits" :key="i">{{ b }}</li>
    </ul>

    <button @click="$emit('addFav')" class="fav-btn">
      Favourite
    </button>

  </div>
</template>

<script>
export default {
  name: "TicketCard",
  props: ['name', 'price', 'benefits', 'featured']
}
</script>

<style>
.card {
  border: 1px solid #ccc;
  padding: 15px;
  border-radius: 10px;
}
.card.featured {
  background-color: #fff5d6;
  border: 2px solid orange;
}
.fav-btn {
  padding: 8px 12px;
  border: none;
  cursor: pointer;
  background-color: #ffefd5;
  border-radius: 6px;
}
</style>
