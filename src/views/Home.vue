<template>
  <div class="home">
    <Callendar
      price="123"
      rating="4.12"
      votes="234"
      available-dates=""
      unavailable-dates=""
      selected-dates=""
      today=""
    />
  </div>
</template>

<script>
import Callendar from "@/components/Callendar.vue";

export default {
  name: "Home",
  components: {
    Callendar,
  },
};
</script>
