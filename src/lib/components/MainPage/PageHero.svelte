<script>
  import { fade } from "svelte/transition";
  let i = 0;
  let tales = ["Valuable", "Unique", "Amazing", "Cool"];
  let changeTale = () => {
    setInterval(() => {
      i++;
      if (i > tales.length - 1) {
        i = 0;
      }
    }, 2000);
  };
  changeTale();
</script>

<div
  class="from-slate-100 via-green-200 to-sky-300 bg-gradient-to-b md:bg-gradient-to-r py-5 pb-6 sm:pb-8 lg:pb-12 md:px-20  "
>
  <div class="mx-auto max-w-screen-2xl px-4 md:px-8 md:py-4">
    <section
      class="flex flex-col justify-between gap-6 sm:gap-10 md:gap-16 lg:flex-row"
    >
      <!-- content - start -->
      <div
        class="flex flex-col justify-center sm:text-center lg:py-12 lg:text-left xl:w-5/12 xl:py-24"
      >
        <h1
          class="text-[#035edd] txt-shadow mb-8 text-4xl text-center md:text-left  font-bold sm:text-5xl md:mb-12 md:text-6xl"
        >
          Create
          {#key i}
            <span class="text-slate-800" in:fade>{tales[i]}</span>
          {/key}
          Projects & Get Hire
        </h1>

        <p
          class="mb-8 leading-relaxed text-gray-500 md:mb-12 lg:w-4/5 xl:text-lg"
        >
          Platform for developers to Upload Projects and get hired by companies.
        </p>

        <div
          class="flex flex-col gap-2.5 sm:flex-row sm:justify-center lg:justify-start"
        >
          <a
            href="/upload"
            class="inline-block rounded-lg bg-[#035edd] px-8 py-3 text-center text-sm font-semibold text-white outline-none ring-indigo-300 transition duration-100 hover:bg-sky-600 focus-visible:ring active:bg-sky-700 md:text-base"
            >Upload</a
          >

          <a
            href="/projects"
            class="inline-block rounded-lg border-2 border-[#035edd] bg-gray-200 px-8 py-3 text-center text-sm font-semibold text-gray-500 outline-none ring-indigo-300 transition duration-100 hover:bg-gray-300 focus-visible:ring active:text-gray-700 md:text-base"
            >Projects</a
          >
        </div>
      </div>
      <!-- content - end -->

      <!-- image - start -->
      <div
        class="h-48 overflow-hidden rounded-lg bg-transparent shadow-lg shadow-slate-500 md:shadow-slate-500  lg:h-3/6 xl:h-3/4 xl:w-1/3"
      >
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img
          src="https://i.pinimg.com/736x/70/eb/74/70eb7470b5ecd27685fb00842c824279.jpg"
          loading="lazy"
          alt="Photo by Fakurian Design"
          class="h-full w-full object-cover object-center "
        />
      </div>
      <!-- image - end -->
    </section>
  </div>
</div>
