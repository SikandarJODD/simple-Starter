<script>
  import supabase from "$lib/db";
  import { onMount } from "svelte";
  $: backData = [];
  onMount(() => {
    getData();
  });
  // .select("showcase_img,first_name,project_name");
  let getData = async () => {
    let { data, error } = await supabase
      .from("studConnect")
      .select("*");
    backData = data;
    if (data) {
      return data;
    }
  };
</script>

<section class="text-gray-600 body-font ">
  <div class="container px-5 py-10 mx-auto">
    <div class="flex flex-wrap w-full mb-10">
      <div class=" w-full mb-6 lg:mb-0">
        <h1
          class="sm:text-4xl text-2xl font-bold title-font mb-2 text-gray-900"
        >
          <span class="text-blue-600">Students</span> Projects
        </h1>
        <hr />
        <div class="h-[2px] w-full bg-[#0c2079] rounded-md" />
      </div>
    </div>

    <div
      class="flex flex-wrap justify-center -m-4 border-2 border-slate-700 rounded-lg px-2 shadow-2xl shadow-sky-400"
    >
      {#await getData()}
        <p />
      {:then data}
        {#each data as item}
            <div class="xl:w-1/5 md:w-1/4 px-3 py-7 w-96 ">
              <div class=" p-6 rounded-lg  card_obj">
                <a href="/projects/{item.id}">
                  <img
                  class="h-40 rounded w-full object-cover object-center mb-5"
                  src={item.showcase_img}
                  alt="content"
                />
                </a>
                <h3
                  class="tracking-widest text-blue-500 font-semibold text-xs  font-mono title-font"
                >
                  {item.first_name}
                </h3>
                <h2
                  class="text-lg text-gray-900 font-mono   title-font crd-title"
                >
                  {item.project_name}
                </h2>
              </div>
            </div>
        {/each}
      {:catch error}
        <p style="color: red">{error.message}</p>
      {/await}
    </div>
  </div>
</section>

<style>
  .card_obj {
    border: 2px solid black;
    border-radius: 10px;
    transition: all 0.3s ease;
  }
  .card_obj:hover {
    background: #56c1f771;
    transform: translate(-7px, -7px);
    transition: all 0.3s ease;
    box-shadow: 7px 7px 0px #001434;
  }
  .card_obj:hover .crd-title {
    transition: all 0.3s ease;
    color: #0557d1;
  }
</style>
