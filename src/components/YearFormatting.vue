<template>
  <span>{{ formattedYear }}</span>
</template>

<script>
export default {
  name: 'YearFormatting',
  props: {
    year: {
      type: Number,
      required: true
    }
  },
  computed: {
    formattedYear() {
      // Check if the year is negative
      if (this.year < 0) {
        return `${Math.abs(this.year)} BCE`; // Convert negative to positive and add "BCE"
      }
      return `${this.year} CE`; // Add "CE" for positive years
    }
  }
}
</script>
