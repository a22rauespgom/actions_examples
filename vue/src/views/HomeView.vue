<template>
  <div class="container">
    <div v-if="selectedNumber !== null" class="selected-number">
      Número: #{{ selectedNumber }}
    </div>
    <div class="grid">
      <button v-for="number in numbers" :key="number" @click="showNumber(number)" class="button">
        {{ number }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      selectedNumber: 0
    }
  },
  methods: {
    showNumber (number) {
      this.selectedNumber = number
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}

.button {
  padding: 10px;
  font-size: 18px;
  background-color: #f0f0f0;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.selected-number {
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
}
</style>
