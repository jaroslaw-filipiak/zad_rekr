<template>
  <div class="callendar">
    <div class="callendar--header"></div>
    <div class="callendar--content">
      <div class="days-names">
        <div>Sun</div>
        <div>Mon</div>
        <div>Tue</div>
        <div>Wed</div>
        <div>Thu</div>
        <div>Fri</div>
        <div>Sat</div>
      </div>
      <div class="days--numbers"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
  },
  setup(props) {
    console.log(props.title);
  },
};
</script>

<style></style>
