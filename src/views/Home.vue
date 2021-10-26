<template>
  <div class="home">
    <ReservationForm
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
import ReservationForm from "../components/ReservationForm.vue";

export default {
  name: "Home",
  components: {
    ReservationForm,
  },
};
</script>

<style scoped lang="scss">
.home {
  @apply flex items-center justify-center pt-10;
}
</style>
