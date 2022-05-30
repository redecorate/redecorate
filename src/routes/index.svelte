<script>
  import Dialog from '$lib/components/Dialog.svelte'

  let dialog
</script>

<main class="flex h-full w-full flex-col items-center justify-center gap-4 bg-[#1e010e]">
  <img src="/favicon.png" alt="Web Refactor" class="w-64 animate-pulse" />
  <h1 class="text-xl font-semibold uppercase tracking-wide text-red-500">Web Refactor</h1>
  <h2 class="text-gray-200">We refactor existing websites to show how better it can be done</h2>

  <button
    on:click={dialog.show}
    class="inline-flex items-center rounded-md border border-transparent bg-indigo-600 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
    >Do not click me!</button
  >
</main>

<Dialog bind:dialog>
  <h2 slot="header" class="text-xl font-semibold text-gray-900">Why did you click me?</h2>

  <div slot="content" class="flex flex-col items-center">
    <p>This will delete everything in your database. This action cannot be undone.</p>
    <img src="/rickroll.gif" alt="you got rick rolled" class="w-64" />
  </div>
  <div slot="footer" class="flex justify-end gap-4">
    <button
      on:click={dialog.hide}
      class="inline-flex items-center rounded-md border border-transparent bg-gray-100 px-4 py-2 text-sm font-medium text-gray-700 shadow-sm hover:bg-gray-200 focus:outline-none focus:ring-2 focus:ring-gray-500 focus:ring-offset-2"
      >Cancel</button
    >

    <button
      on:click={dialog.hide}
      class="inline-flex items-center rounded-md border border-transparent bg-red-600 px-4 py-2 text-sm font-medium text-white shadow-sm hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2"
      >Confirm</button
    >
  </div>
</Dialog>
