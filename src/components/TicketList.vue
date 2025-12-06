<template>
  <div class="list">
    <ticket-card
      v-for="t in tickets"
      :key="t.id"
      :name="t.name"
      :price="t.price"
      :benefits="t.benefits"
      :featured="t.featured"
      @addFav="$emit('favourite')"
    />
  </div>
</template>

<script>
import TicketCard from './TicketCard.vue'

export default {
  name: "TicketList",
  props: ['tickets'],
  components: {
    TicketCard
  }
}
</script>

<style>
.list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>
