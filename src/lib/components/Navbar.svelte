<script>
  import { fade, scale } from "svelte/transition";
  import { page } from "$app/stores";
  $: routeId = $page.route.id;

  let navs = [
    {
      name: "Home",
      link: "/",
    },
    {
      name: "Projects",
      link: "/projects",
    },
    {
      name: "Upload",
      link: "/upload",
    },
    {
      name: "About Us",
      link: "/about",
    },
  ];
  $: lenheight = 0;
  $: TotalVal = 0;
  let display = "hidden transition-all duration-300";
  let handleMouse = (e) => {
    TotalVal = Math.floor(e.pageY - lenheight);
    if (TotalVal <= 50) {
      // console.log(display, TotalVal);
      display = "flex transition-all duration-300";
    } else if (TotalVal > 50) {
      // console.log(display, TotalVal);
      display = "hidden transition-all duration-300";
    }
  };
</script>

<svelte:body on:mousemove={handleMouse} />

<svelte:window bind:scrollY={lenheight} />
<div
  class=" z-10 navbar sticky top-0 rounded-md w-[90%] transition-all duration-300  m-auto {Math.floor(
    lenheight
  ) > 120
    ? 'backdrop-blur-md bg-[#129afbab] border-2 border-gray-900 md:w-[60%]  top-3 transition-all duration-200'
    : ' '}  "
>
  <div class="navbar-start">
    <div class="dropdown">
      <!-- svelte-ignore a11y-no-noninteractive-tabindex -->
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label tabindex="0" class="btn btn-ghost lg:hidden">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          ><path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h8m-8 6h16"
          /></svg
        >
      </label>
      <!-- svelte-ignore a11y-no-noninteractive-tabindex -->
      <ul
        tabindex="0"
        class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-base-100 rounded-box w-52"
      >
        <!-- Phone View  -->
        {#each navs as nav}
          <li>
            <a
              href={nav.link}
              class=" {Math.floor(lenheight) > 150
                ? '  text-black transition-all duration-150'
                : ''} "
              class:act={routeId === nav.link}>{nav.name}</a
            >
          </li>
        {/each}
      </ul>
    </div>
    <a
      href="/"
      class="btn btn-ghost normal-case text-xl bg-base-200 md:bg-slate-700  md:text-2xl font-bold text-sky-500"
      >Pro - Stud</a
    >
  </div>
  <div class="navbar-center hidden lg:flex">
    <ul class="menu menu-horizontal px-1">
      {#each navs as nav}
        <li>
          <a
            href={nav.link}
            class="btn btn-ghost {Math.floor(lenheight) > 150
              ? '  text-black transition-all duration-150'
              : ''} "
            class:act={routeId === nav.link}>{nav.name}</a
          >
        </li>
      {/each}
    </ul>
  </div>
</div>

<style>
  .act {
    color: hsl(224, 96%, 22%);
    border: 2px solid #03256e;
    background: #0131531e;
    margin: 0 10px;
  }
</style>
