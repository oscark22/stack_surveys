<script lang="ts">
	import Chart from 'chart.js/auto';
	import type { List } from 'postcss/lib/list';
	import list from 'postcss/lib/list';
  import { onMount } from 'svelte';
	import { get } from 'svelte/store';

  let canvas: HTMLCanvasElement;
  
  onMount(async () => {
    const chartData = await (await fetch('http://127.0.0.1:8000/loved_languages/10')).json()
    const labels = Object.keys(chartData)

    console.log(chartData)

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
      for (const [language, responses] of Object.entries(chartData[label]["data"])) {
        let response = responses as Responses

        place += 1
        if (!itemsData.hasOwnProperty(language)) {
          itemsData[language] = {
            index: [],
            place: Array(5).fill(NaN),
            num_responses: Array(5).fill(NaN),
            total_responses: Array(5).fill(NaN)
          }         
        }
        itemsData[language]["index"].push(index)
        itemsData[language]["place"][index] = place
        itemsData[language]["num_responses"][index] = response["num_responses"]
        itemsData[language]["total_responses"][index] = response["total_responses"]
      }
      index += 1
    }
    console.log(itemsData)

    let datasets = Array()
    for (const [language, object] of Object.entries(itemsData)) {
      const itemData = object as ItemData

      console.log(itemData["place"])

      datasets.push({
        label: language,
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
          tension: 0.25,
        },
      },
    }

    new Chart(canvas, {
      type: 'line',
      data: data,
      options: options
    });
  });

  export let height: number;
</script>

<canvas bind:this={canvas} height={height}>
  <p>Hello Fallback World</p>
</canvas>


