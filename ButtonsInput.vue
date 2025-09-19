<template>
  <div class="dartboard-container">
    <canvas id="dartboard" @click="selectScore" width="500" height="500"></canvas>
  </div>
</template>

<script>
export default {
  name: 'ButtonsInput',
  methods: {
    selectScore(event) {
      const canvas = document.getElementById('dartboard');
      const rect = canvas.getBoundingClientRect();
      const x = event.clientX - rect.left;
      const y = event.clientY - rect.top;
      // Logic to determine the score based on the (x, y) coordinates
      console.log(`Score selected at (${x}, ${y})`);
    },
    drawDartboard() {
      const canvas = document.getElementById('dartboard');
      const context = canvas.getContext('2d');
      // Logic to draw the dartboard on the canvas
      context.clearRect(0, 0, canvas.width, canvas.height);
      // Draw dartboard here
    },
  },
  mounted() {
    this.drawDartboard();
  },
};
</script>

<style scoped>
.dartboard-container {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>