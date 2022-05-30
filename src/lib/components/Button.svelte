<script>
  export let isPrimary = true
  export let isSecondary = false
  export let size = 'md'
  export let color = 'indigo'

  let classes = `inline-flex items-center border border-transparent font-medium rounded-md focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-${color}-500`

  if (isSecondary) {
    classes += ` text-${color}-700 bg-${color}-100 hover:bg-${color}-200`
  } else if (isPrimary) {
    classes += ` text-white bg-${color}-600 hover:bg-${color}-700 shadow-sm`
  }
  if (size === 'sm') {
    classes += ' px-3 py-2 text-sm'
  } else if (size === 'md') {
    classes += ' px-4 py-2 text-sm'
  } else if (size === 'lg') {
    classes += ' px-4 py-2 text-base'
  } else if (size === 'xl') {
    classes += ' px-6 py-3 text-base'
  }
</script>

<button class={classes} on:click>
  <slot />
</button>
