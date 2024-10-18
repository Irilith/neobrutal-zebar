<script lang="ts">
  import type { GlazeWmOutput } from "zebar";

  let { glazewm }: { glazewm: GlazeWmOutput } = $props();
</script>

{#if glazewm}
  <div class="flex items-center gap-1">
    {#each glazewm.allWorkspaces as workspace}
      {#each workspace.children as child}
        {#if child.type == "window" && child.processName.toLowerCase() === "spotify"}
          <span class="max-w-md truncate">
            {#if !child.title.toLowerCase().includes("spotify")}
              <i class="ti ti-music text-zb-spotify-playing"></i>
              {child.title}
            {/if}
          </span>
        {/if}
      {/each}
    {/each}
  </div>
{/if}
