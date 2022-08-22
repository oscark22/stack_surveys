<script lang="ts">
  import Chart from 'chart.js/auto';
  import { onMount } from 'svelte'

  let canvas: HTMLCanvasElement;
  
  const labels = [1,2,3,4,5,6,7];
  const chartData = {
    labels: labels,
    datasets: [{
      label: 'My First Dataset',
      data: [65, 59, 80, 81, 56, 55, 40],
      fill: false,
      borderColor: 'rgb(75, 192, 192)',
      tension: 0.1,
    }],
  };
  
  onMount(() => {
    new Chart(canvas, {
      type: 'line',
      data: chartData
    });
  });
</script>

<canvas bind:this={canvas} width="400" height="100">
  <p>Hello Fallback World</p>
</canvas>