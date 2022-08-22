<script lang="ts">
  import { onMount } from 'svelte';
  import Chart from 'chart.js/auto';

  let canvas: HTMLCanvasElement;
  
  const labels = [1,2,3,4,5,6,7];
  const chartData = {
    labels: labels,
    datasets: [{
      label: 'Donuts',
      data: [65, 59, 80, 81, 56, 55, 40],
      borderColor: 'rgb(75, 192, 192, 0.6)',
      pointBackgroundColor: 'rgb(75, 192, 192)',
      backgroundColor: 'rgb(75, 192, 192, 0.2)',
      fill: true,
    }],
  };
  
  onMount(() => {
    new Chart(canvas, {
      type: 'line',
      data: chartData,
      options: {
        elements: {
          point: {
            radius: 4,
          },
          line: {
            tension: 0.25,
          },
        }
      }
    });
  });
</script>

<canvas bind:this={canvas}>
  <p>Hello Fallback World</p>
</canvas>