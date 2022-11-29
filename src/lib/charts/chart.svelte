<script lang="ts">
	import Chart from 'chart.js/auto';
  import { onMount } from 'svelte';

  let canvas: HTMLCanvasElement;
  
  onMount(async () => {
    const chartData = await (await fetch(url)).json()
    const labels = Object.keys(chartData)

    interface Responses {
      num_responses: string,
      total_responses: string    
    }

    interface ItemData {
      index: number[],
      place: number[],
      num_responses: number[],
      total_responses: number[]
    }

    let itemsData = Object(), index = 0

    for (const label of labels) {
      let place = 0
      for (const [item, responses] of Object.entries(chartData[label]["data"])) {
        let response = responses as Responses

        place += 1
        if (!itemsData.hasOwnProperty(item)) {
          itemsData[item] = {
            index: [],
            place: Array(5).fill(NaN),
            num_responses: Array(5).fill(NaN),
            total_responses: Array(5).fill(NaN)
          }         
        }
        itemsData[item]["index"].push(index)
        itemsData[item]["place"][index] = place
        itemsData[item]["num_responses"][index] = response["num_responses"]
        itemsData[item]["total_responses"][index] = response["total_responses"]
      }
      index += 1
    }

    let datasets = Array()
    for (const [item, object] of Object.entries(itemsData)) {
      const itemData = object as ItemData

      datasets.push({
        label: item,
        data: itemData["place"]
      })
    }

    const data = {
      labels: labels,
      datasets: datasets
    }

    const options = {
      scales: {
        x: {
          title: {
            display: true,
            text: "Year"
          }
        },
        y: {
          reverse: true,
          title: {
            display: true,
            text: "Place in ranking"
          }
        }
      },
      elements: {
        point: {
          radius: 5,
        },
        line: {
          tension: 0.15,
        },
      },
    }

    new Chart(canvas, {
      type: 'line',
      data: data,
      options: options
    });
  });

  let height: number;
  let url: string;

  export { height, url };
</script>

<canvas bind:this={canvas} height={height}>
  <p>Hello Fallback World</p>
</canvas>
