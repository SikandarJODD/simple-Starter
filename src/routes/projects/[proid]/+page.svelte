<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";
  import supabase from "$lib/db";
  $: rID = $page.params;
  $: console.log(rID, rID.proid);
  $: fufi = [];
  onMount(() => {
    getData();
  });
  let getData = async () => {
    let { data, error } = await supabase
      .from("studConnect")
      .select("*")
      .eq("id", rID.proid);
    console.log("bhai", data);
    fufi = data;
    if (data) {
      return data;
    }
  };
  $: fufiData = fufi[0];
</script>

{#await getData() then data}
  <div class="bg-white py-6 sm:py-8 lg:py-12">
    <div class="mx-auto max-w-screen-md px-4 md:px-8">
      <!-- svelte-ignore a11y-missing-attribute -->
      <a
        class="relative block overflow-hidden rounded-xl md:h-96 h-64 popy"
        style="background-image: url({data[0].showcase_img});"
      >
        <div class="absolute inset-0 bg-black/25" />

        <div
          class="relative flex items-start justify-between p-4 sm:p-6 lg:p-8"
        >
          <div class="sm:pt-18 pt-44 text-white lg:pt-72">
            <h3 class="text-xl font-bold sm:text-2xl">{data[0].first_name}</h3>

            <p class="text-sm">{data[0].created_at}</p>
          </div>

          <div class="flex">
            <a
              href={data[0].website_link}
              target="_blank"
              class="text-white mx-1 transition duration-100 hover:text-gray-900 active:text-gray-600"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-6 w-6"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"
                />
              </svg>
            </a>

            <a
              href={data[0].github_link}
              target="_blank"
              class="text-white mx-1 transition duration-100 hover:text-gray-900 active:text-gray-600"
            >
              <svg
                class="h-5 w-5"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                />
              </svg>
            </a>
          </div>
        </div>
      </a>

      <!-- <div class="relative mb-6 overflow-hidden rounded-lg bg-gray-100 shadow-lg md:mb-8">
        <img src="https://images.unsplash.com/photo-1593508512255-86ab42a8e620?auto=format&q=75&fit=crop&w=600&h=350" loading="lazy" alt="Photo by Minh Pham" class="h-full w-full object-cover object-center" />
      </div> -->

      <h1
        class="mb-4 text-center text-2xl font-bold text-gray-800 mt-3 sm:text-4xl md:mb-6"
      >
        {data[0].project_name}
      </h1>

      <p class="mb-6 text-gray-500 sm:text-lg md:mb-8">
        {data[0].project_desc}
      </p>
    </div>
  </div>
{/await}

<style>
  .popy {
    height: 400px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  @media (max-width: 640px) {
    .popy {
      height: 270px;
    }
  }
</style>
