<script context="module">

  export let topologyMap
  export let strategy

  let iotes = createIotesCore(topologyMap, strategy)
  
</script>

<script>
  import { readable } from 'svelte/store'
  import { createIotes as createIotesCore } from '@iotes/core'

  export const host = readable({}, () => {
    hostSubscribe((state) => set(state))
    
    return () => {}
  })

  export const device = readable({}, () => {
    deviceSubscribe((state) => set(state))
    
    return () => {}
  })

  const {
    hostSubscribe,
    deviceSubscribe,
  } = iotes
  
</script>