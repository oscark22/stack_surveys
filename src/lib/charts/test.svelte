<script lang="ts">
	import Chart from 'chart.js/auto';
  import { onMount } from 'svelte';

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
        },
      }
    });
  });
</script>

<canvas bind:this={canvas} height="100">
  <p>Hello Fallback World</p>
</canvas>
