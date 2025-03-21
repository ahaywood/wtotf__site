<script lang="ts">
  import Icon from "./Icon.svelte";
  let { code }: { code: string } = $props();
  let isCopied = $state(false);
</script>

<div class="bg-lightFuchsiaPink font-mono font-bold flex items-center justify-between h-[60px] px-6 w-full max-w-[470px] mx-auto">
  <pre>{code}</pre>
  <button class="text-brightBlue cursor-pointer" onclick={() => {
    navigator.clipboard.writeText(code);
    isCopied = true;
    setTimeout(() => {
      isCopied = false;
    }, 2000);
  }}>
    {#if isCopied}
      <Icon id="check" size={24} />
    {:else}
      <Icon id="clipboard" size={24} />
    {/if}
  </button>
</div>