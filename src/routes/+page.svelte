<script lang="ts">
  import Banner from "$lib/banner.svelte";
  import Chart from "$lib/charts/chart.svelte";
  import Title from "$lib/title.svelte";
</script>


<Title 
  title="Stack Developer Survey" 
  subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit." 
/>
<div class="flex flex-col lg:flex-row lg:space-x-6">
  <div class="text-white lg:w-7/12 rounded-md p-6 lg:p-8 lg:pb-40 mb-6 sm:mb-4 bg-gradient-to-tl from-emerald-500 to-blue-600">
    <!-- title card -->
    <h1 class="text-xl lg:text-2xl font-semibold">
      About this webpage
    </h1>
    <p class="bg-white w-8 h-0.5 my-2" />
    <!-- body card -->
    <p class="leading-relaxed pt-6">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam possimus necessitatibus.
    </p>
    <p class="leading-relaxed pt-6">
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sed temporibus distinctio sunt odio, itaque nemo excepturi at laudantium quam quia, id commodi soluta. Reprehenderit eius voluptate ea quam deleniti similique.
    </p>
    <br>
    <button class="bg-slate-900 py-2 px-8 rounded-md hover:bg-blue-900">
      Overview ->
    </button>
  </div>
  <div class="text-white lg:w-5/12 rounded-md p-6 lg:p-8 lg:pb-40 mb-6 sm:mb-4 bg-gradient-to-tl from-purple-500 to-blue-600">
    <!-- title card -->
    <h1 class="text-xl lg:text-2xl font-semibold">
      About licencing
    </h1>
    <p class="bg-white w-8 h-0.5 my-2" />
    <!-- body card -->
    <p class="leading-relaxed pt-6">
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptatum libero eum fugit laborum fuga. Veniam ex ab eaque sunt culpa maxime nulla repellendus sapiente minus, molestiae, minima hic eveniet vitae.
    </p>
    <p class="leading-relaxed pt-6">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias, totam hic et voluptatem corporis, molestias tempora quae culpa temporibus nisi odit? Sed quas explicabo quibusdam sapiente aut corrupti aperiam ducimus.
    </p>
  </div>
</div>
<div class="mt-32 lg:mt-4">
  <Banner
    title='Technology'
    from_color='from-cyan-500'
    to_color='to-blue-500'
  />
</div>
<div class="flex flex-col mt-6">
  <p class="text-xl">
    Most loved, dreaded and wanted
  </p>
  <p class="bg-black w-8 h-0.5 my-2" />
</div>
<div>
  <div class="flex mt-10 mb-4 justify-center">
    Programming, scripting, and markup languages
  </div>
  <Chart url="http://127.0.0.1:8000/loved_languages/10" height={100} />
</div>
<div>
  <div class="flex mt-10 mb-4 justify-center">
    Databases
  </div>
  <Chart url="http://127.0.0.1:8000/loved_databases/10" height={100} />
</div>
<div>
  <div class="flex mt-10 mb-4 justify-center">
    Web frameworks and technologies
  </div>
  <Chart url="http://127.0.0.1:8000/loved_frameworks/10" height={100} />
</div>
