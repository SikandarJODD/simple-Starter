<script>
  let featureData = [
    {
      title: "Connection",
      description:
        "Students can connect with other students and teachers to get help with their Projects",
      svgDetail: `<svg
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
          </svg>`,
    },
    {
      title: "Innovation",
      description:
        "Projects are innovative and creative. They are not just a copy of other projects",
      svgDetail: `<svg
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
              d="M18.364 5.636l-3.536 3.536m0 5.656l3.536 3.536M9.172 9.172L5.636 5.636m3.536 9.192l-3.536 3.536M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-5 0a4 4 0 11-8 0 4 4 0 018 0z"
            />
          </svg>`,
    },

    {
      title: "Quality",
      description: "Hiring is based on quality of Projects Students Build",
      svgDetail: `<svg
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
              d="M3 15a4 4 0 004 4h9a5 5 0 10-.1-9.999 5.002 5.002 0 10-9.78 2.096A4.001 4.001 0 003 15z"
            />
          </svg>`,
    },
    {
      title: "Sector",
      description:
        "Students can Upload Projects in any Sector. They can also search for Projects in any Sector",
      svgDetail: `<svg
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
              d="M13 10V3L4 14h7v7l9-11h-7z"
            />
          </svg>`,
    },
  ];
</script>

<div class="bg-white py-6 sm:py-8 lg:py-12">
  <div class="mx-auto max-w-screen-2xl px-4 md:px-32">
    <!-- text - start -->
    <div class="mb-10 md:mb-16">
      <h2
        class="mb-4 text-center text-2xl font-bold text-gray-800 md:mb-6 lg:text-4xl"
      >
        Our Features
      </h2>

      <!-- <p class="mx-auto max-w-screen-md text-center text-gray-500 md:text-lg">
        This is a section of some simple filler text, also known as placeholder
        text. It shares some characteristics of a real written text but is
        random or otherwise generated.
      </p> -->
    </div>
    <!-- text - end -->

    <div class="grid gap-8 sm:grid-cols-2 md:gap-12 xl:grid-cols-3 xl:gap-16">
      <!-- feature - start -->
      {#each featureData as item}
        <div
          class="flex gap-4 md:gap-6 md:hover:bg-sky-300 md:px-4  md:py-3 rounded-lg transition-all duration-300"
        >
          <div
            class="flex h-12 w-12 shrink-0 items-center justify-center rounded-lg bg-indigo-500 text-white shadow-lg md:h-14 md:w-14 md:rounded-xl"
          >
            {@html item.svgDetail}
          </div>

          <div>
            <h3 class="mb-2 text-lg font-semibold md:text-xl">{item.title}</h3>
            <p class="mb-2 text-gray-500">
              {item.description}
            </p>
          </div>
        </div>
        <!-- feature - end -->
      {/each}
    </div>
  </div>
</div>
