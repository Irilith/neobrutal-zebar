<script lang="ts">
  import type { GlazeWmOutput } from "zebar";

  let { glazewm }: { glazewm: GlazeWmOutput } = $props();

  function capitalizeFirstLetter(str) {
    if (!str) return "";
    return str.charAt(0).toUpperCase() + str.slice(1);
  }
</script>

{#if glazewm}
  {#each glazewm.focusedWorkspace.children as child}
    {#if child.type === "window" && child.hasFocus}
      <span class="max-w-md truncate">
        {capitalizeFirstLetter(child.processName)} - {child.title}
      </span>
    {/if}
  {/each}
{/if}
