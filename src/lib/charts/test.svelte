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

    let occurrences = Object(), index = 0
    for (const label of labels) {
      let place = 0
      for (const [language, responses] of Object.entries(chartData[label]["data"])) {
        let response = responses as Responses

        place += 1
        if (occurrences.hasOwnProperty(language)) {
          occurrences[language].push([index, place, response["num_responses"], response["total_responses"]])
        } else {
          occurrences[language] = [[index, place, response["num_responses"], response["total_responses"]]]
        }
      }
      index += 1
    }
    console.log(occurrences)

    let datasets = Array()
    // for (const [language, list] of Object.entries(occurrences)) {
    //   const data = list as Array<String | Number>

    //   datasets.push({
    //     label: language,
    //     data: data[1],
    //   })
    // }

    const data = {
      labels: labels,
      datasets: datasets
    }

    const options = {
      elements: {
        point: {
          radius: 4,
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


