<template>
  <form action="">
    <div class="reservation-form">
      <div class="reservation-form--inner">
        <div class="reservation-form--header">
          <div class="reservation-form--price">298 zł</div>
          <div class="reservation-form--rating">
            <div class="stars">
              <div class="star">
                <svg width="24" height="24" viewBox="0 0 24 24">
                  <path
                    d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"
                  />
                </svg>
              </div>

              <div class="star">
                <svg width="24" height="24" viewBox="0 0 24 24">
                  <path
                    d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"
                  />
                </svg>
              </div>

              <div class="star">
                <svg width="24" height="24" viewBox="0 0 24 24">
                  <path
                    d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"
                  />
                </svg>
              </div>

              <div class="star">
                <svg width="24" height="24" viewBox="0 0 24 24">
                  <path
                    d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"
                  />
                </svg>
              </div>

              <div class="star">
                <svg width="24" height="24" viewBox="0 0 24 24">
                  <path
                    d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"
                  />
                </svg>
              </div>
            </div>
            <div class="stars--average-rate">123</div>
          </div>
        </div>
        <div class="reservation-form--dates">
          <p class="mb-3 mt-5 font-semibold">Dates</p>
          <div class="reservation-form--dates--inner">
            <div @click="callendarVisibility" class="date-from">Check In</div>
            <div>
              <svg
                width="24"
                height="24"
                fill-rule="evenodd"
                clip-rule="evenodd"
              >
                <path
                  d="M21.883 12l-7.527 6.235.644.765 9-7.521-9-7.479-.645.764 7.529 6.236h-21.884v1h21.883z"
                />
              </svg>
            </div>
            <div @click="callendarVisibility" class="date-to">Check Out</div>
          </div>
          <div v-if="isCallendarVisible" class="callendar-box">
            <Callendar />
          </div>
        </div>
        <p></p>

        <div class="btn btn__submit">Check availability</div>
      </div>
    </div>
  </form>
</template>

<script>
import Callendar from "./Callendar.vue";
export default {
  props: [
    "price",
    "rating",
    "votes",
    "available-dates",
    "unavailable-dates",
    "selected-dates",
    "today",
  ],
  components: { Callendar },
  data() {
    return {
      isCallendarVisible: false,
    };
  },
  methods: {
    callendarVisibility() {
      this.isCallendarVisible = !this.isCallendarVisible;
    },
  },
};
</script>

<style scoped lang="scss">
.reservation-form {
  @apply p-5;
  width: 444px;
  background-color: #ececec;

  &--inner {
    @apply border border-gray-300 p-5;
  }

  &--header {
    @apply border-b border-gray-300 pb-5;
  }

  &--dates--inner {
    @apply border border-gray-300 p-3 flex items-center justify-between text-xl text-gray-500;
  }

  &--price {
    @apply text-2xl font-bold mb-1;
  }

  &--rating {
    @apply flex items-center justify-start;
  }

  &--dates {
    @apply relative;

    .callendar-box {
      @apply border border-red-600 absolute top-24 bg-blue-50 z-10;
      width: 90%;
      left: 5%;
    }
  }
}

.stars {
  @apply flex items-center justify-start;

  .star {
    @apply w-4;

    svg {
      @apply transform scale-50;
      transform-origin: left center;
    }
    path {
      fill: 367c7e;
    }
  }

  &--average-rate {
    @apply text-base font-semibold ml-1;
  }
}

.btn {
  @apply inline-block bg-red-600 p-4 w-full rounded-lg mt-5 text-white text-center cursor-pointer font-semibold text-lg hover:opacity-80;

  &::selection {
    @apply bg-transparent;
  }
}

.date-from,
.date-to {
  @apply cursor-pointer hover:opacity-80;
  &::selection {
    @apply bg-transparent;
    outline: none;
  }
}
</style>
