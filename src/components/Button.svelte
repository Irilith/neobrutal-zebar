<script lang="ts">
  type ButtonProps = {
    iconClass: string;
    label?: string;
    callback?: () => void;
    class: string;
  };

  let { iconClass, label, callback, ...rest }: ButtonProps = $props();
</script>

<button
  class="flex items-center bg-blend-30 border border-zb-border rounded-base shadow-button hover:translate-x-boxShadowX hover:translate-y-boxShadowY hover:shadow-none p-1 {rest.class}"
  onclick={callback}
  aria-label={label}
>
  <i class="ti ti-{iconClass}"></i>
  {#if label}
    <span>{label}</span>
  {/if}
</button>

<style>
  button {
    border: none;
    border-radius: 6px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
    padding: 4px 8px;
    cursor: pointer;
    transition:
      background-color 0.3s,
      transform 0.2s;
    font-size: 0.875rem;
  }

  button:hover {
    background-color: var(--button-hover-bg, #555);
    transform: translateY(-1px);
  }

  .focused {
    background-color: var(--focused-bg, #ffcc00);
    color: #fff;
  }
</style>
