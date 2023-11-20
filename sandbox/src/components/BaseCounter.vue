<script>
export default {
  data: () => ({
    count: 10,
    counterTitle: 'Counter Standard',
    incrementAmount: 1
  }),
  computed: {
    displayTitle() {
      if (this.count > 20) {
        return 'Counter High'
      } else {
        return 'Counter Low'
      }
    },
    optimizedIncrementAmount() {
      return this.displayTitle.length * this.incrementAmount
    }
  },
  methods: {
    incrementCount() {
      this.count += this.incrementAmount
    }
  }
}
</script>

<template>
  <h1>{{ displayTitle }}</h1>
  <p :data-increment-by="incrementAmount">{{ count }}</p>
  <button @click="incrementCount">Increment Count</button>
  <h1>{{ incrementAmount }}</h1>
  <p>{{ optimizedIncrementAmount }}</p>
  <div>
    <label for="incrementAmount">Increment by:</label>
    <input type="number" v-model="incrementAmount" />
  </div>
  <hr />
</template>
