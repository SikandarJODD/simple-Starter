<script>
  import supabase from "$lib/db";
  import { onMount } from "svelte";
  let projectData = {
    created_at: new Date(),
    first_name: "",
    college_name: "",
    email: "",
    project_name: "",
    project_tags: "",
    project_desc: "",
    github_link: "",
    website_link: "",
    showcase_img: "",
  };
  let studProData = [
    "https://i.pinimg.com/564x/34/ac/14/34ac14141d8a9811a651c50e23aef2d4.jpg",
    "https://i.pinimg.com/564x/63/6a/09/636a09d9c32d34f9b4037e1fac5db6cf.jpg",
    "https://i.pinimg.com/564x/ad/ba/6d/adba6d6b6f7192aaf60f50372f00b9d8.jpg",
    "https://i.pinimg.com/564x/57/3c/af/573cafd440c1dd21f462ff7339ccaa19.jpg",
    "https://i.pinimg.com/564x/f3/68/ac/f368aca0fe4f7bb47c982a1bf1062e2b.jpg",
    "https://i.pinimg.com/564x/0a/86/9a/0a869a26132aa2982c57b958e71d80b9.jpg",
    "https://i.pinimg.com/564x/0a/c3/f6/0ac3f68e2c8b88489400978f98c3c77d.jpg",
    "https://i.pinimg.com/564x/4d/7f/24/4d7f24025c9f964960747da8a64d8ceb.jpg",
    "https://i.pinimg.com/564x/05/de/31/05de315a05b6b81880ca5aefdeac762e.jpg",
    "https://i.pinimg.com/564x/af/69/ab/af69ab11f4525ccc68d07a9ef0ccb589.jpg",
    "https://i.pinimg.com/564x/be/8d/18/be8d1804bb1ffd71e8aef9ea37540cb5.jpg",
    "https://i.pinimg.com/564x/35/ca/ed/35caed9ed16376c0a35e93354952759e.jpg",
  ];

  let uploadData = async () => {
    let mt = Math.floor(Math.random() * 11);
    if (projectData.showcase_img === "") {
      projectData.showcase_img = studProData[mt];
    }
    const { data, error } = await supabase
      .from("studConnect")
      .insert([projectData]);
    if (data) {
      console.log("Data Inserted");
    }
    if (error) {
      console.log("Error", error);
    }
  };
</script>

<div class="bg-white py-6 sm:py-8 lg:py-12">
  <div class="mx-auto  max-w-screen-2xl px-4 md:px-8">
    <!-- text - start -->
    <div class="mb-10 md:mb-16">
      <h2
        class="mb-4 text-center text-2xl font-bold text-blue-500 md:mb-6 lg:text-3xl"
      >
        Project Submission Form
      </h2>

      <p class="mx-auto max-w-screen-md text-center text-gray-500 md:text-lg">
        This Details will be showcase on website and your Identiy will be added
        & Send to recuiter for further process.
      </p>
    </div>
    <!-- text - end -->

    <!-- form - start -->
    <form
      on:submit|preventDefault={uploadData}
      class="mx-auto p-6 rounded-xl shadow-md shadow-slate-400 border-2 border-slate-900 grid max-w-screen-md gap-4 sm:grid-cols-2"
    >
      <div class="sm:col-span-2">
        <label
          for="first-name"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Full name*
        </label>
        <input
          bind:value={projectData.first_name}
          name="first-name"
          class="w-full  rounded border border-sl bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100 "
        />
      </div>

      <div class="sm:col-span-2">
        <label
          for="college"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >College Name</label
        >
        <input
          bind:value={projectData.college_name}
          name="college"
          class="w-full rounded border bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100"
        />
      </div>

      <div class="sm:col-span-2">
        <label
          for="email"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Email*</label
        >
        <input
          bind:value={projectData.email}
          name="email"
          class="w-full rounded border bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100"
        />
      </div>

      <div class="sm:col-span-2">
        <label
          for="project_n"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Project Name*</label
        >
        <input
          bind:value={projectData.project_name}
          name="project_n"
          class="w-full rounded border bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100"
        />
      </div>
      <div class="sm:col-span-2">
        <label
          for="project_t"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Project Tags <span class="text-red-600">(seperated by comma)</span>
        </label>
        <input
          bind:value={projectData.project_tags}
          name="project_t"
          class="w-full rounded border bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100"
        />
      </div>

      <div class="sm:col-span-2">
        <label
          for="message"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Project Description</label
        >
        <textarea
          bind:value={projectData.project_desc}
          name="message"
          class="h-64 w-full rounded border bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100"
        />
      </div>
      <div class="sm:col-span-2">
        <label
          for="github-link"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Github Link
        </label>
        <input
          bind:value={projectData.github_link}
          name="github-link"
          class="w-full  rounded border-2 border-sky-400 border-sl bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100 "
        />
      </div>
      <div class="sm:col-span-2">
        <label
          for="website-link"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Website Hosted Link (if any)
        </label>
        <input
          bind:value={projectData.website_link}
          name="website-link"
          class="w-full  rounded border-2 border-sky-400 border-sl bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100 "
        />
      </div>
      <div class="sm:col-span-2">
        <label
          for="project-img"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Showcase Image (if any)
        </label>
        <input
          bind:value={projectData.showcase_img}
          name="project-img"
          class="w-full  rounded border-2 border-sky-400 border-sl bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100 "
        />
      </div>
      <div class="flex items-center justify-between sm:col-span-2">
        <button
          type="submit"
          class="inline-block rounded-lg border-2 border-gray-900 text-gray-900 px-8 py-3 text-center text-sm font-semibold outline-none  hover:bg-sky-500 hover:scale-110  transition duration-200 md:text-base"
          >Send</button
        >

        <span class="text-sm text-gray-500">*Required</span>
      </div>
    </form>
    <!-- form - end -->
  </div>
</div>

<style>
  label {
    font-weight: 700;
    color: rgb(44, 47, 52);
  }
</style>
