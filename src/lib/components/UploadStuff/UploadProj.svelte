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
      class="mx-auto p-6 rounded-xl shadow-md shadow-slate-400 border-2 border-slate-900 grid max-w-screen-md gap-4 sm:grid-cols-2"
    >
      <div class="sm:col-span-2">
        <label
          for="first-name"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Full name*
        </label>
        <input
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
          name="email"
          class="w-full rounded border bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100"
        />
      </div>

      <div class="sm:col-span-2">
        <label
          for="subject"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Project Name*</label
        >
        <input
          name="subject"
          class="w-full rounded border bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100"
        />
      </div>
      <div class="sm:col-span-2">
        <label
          for="subject"
          class="mb-2 inline-block text-sm text-gray-800 sm:text-base"
          >Project Tags <span class="text-red-600">(seperated by comma)</span>
        </label>
        <input
          name="subject"
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
          name="project-img"
          class="w-full  rounded border-2 border-sky-400 border-sl bg-gray-50 px-3 py-2 text-gray-800 outline-none focus:border-2 focus:border-sky-400 transition duration-100 "
        />
      </div>
      <div class="flex items-center justify-between sm:col-span-2">
        <button
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
