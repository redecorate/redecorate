<script>
  import Dialog from '$lib/components/Dialog.svelte'
  import Button from '$lib/components/Button.svelte'

  let dialog
</script>

<main class="flex h-full w-full flex-col items-center justify-center gap-4 bg-[#1e010e]">
  <img src="/favicon.png" alt="Web Refactor" class="w-64 animate-pulse" />
  <h1 class="text-xl font-semibold uppercase tracking-wide text-red-500">Web Refactor</h1>
  <h2 class="text-gray-200">We refactor existing websites to show how better it can be done</h2>

  <Button on:click={dialog.show} size="lg">Open Dialog</Button>
</main>

<Dialog bind:dialog>
  <h2 slot="header" class="text-xl font-semibold text-gray-900">Are you sure?</h2>

  <p slot="content" class="">
    This will delete everything in your database. This action cannot be undone.
  </p>
  <div slot="footer" class="flex justify-end gap-4">
    <Button on:click={dialog.hide} isSecondary color="gray">Cancel</Button>

    <Button on:click={dialog.hide} color="red">Confirm</Button>
  </div>
</Dialog>
