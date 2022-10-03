<script lang="ts">
  import Banner from "$lib/banner.svelte";
  import Test from "$lib/charts/test.svelte";
  import Title from "$lib/title.svelte";
</script>

<div class="flex-1">
  <div class="h-full p-4 lg:p-6">
    <div class="flex-1 h-full">
      <Title 
        title="Stack Developer Survey" 
        subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit." 
      />
      <div class="lg:flex lg:space-x-6">
        <div class="text-white lg:w-7/12 rounded-md p-6 lg:p-8 pb-20 lg:pb-40 mb-40 sm:mb-4 bg-gradient-to-tl from-emerald-500 to-blue-600">
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
          <button class="bg-slate-900 py-2 px-8 rounded-md">
            Overview ->
          </button>
        </div>
        <div class="text-white lg:w-5/12 rounded-md p-6 lg:p-8 pb-40 lg:pb-40 mb-4 bg-gradient-to-tl from-purple-500 to-blue-600">
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
      <div class="mt-20">
        <Banner
          title='Developer profile'
          from_color='from-cyan-600'
          to_color='to-green-500'
        />
      </div>
      <div class="flex mt-6">
        <p class="text-xl">
          Educational attainment
        </p>
      </div>
      <div class="h-96">
        <Test />
      </div>
    </div>
  </div>
</div>
