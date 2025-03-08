<script lang="ts">
  let { id, size = 24, props }: { id: string, size?: number, props?: any } = $props();
</script>

<svg {...props} width={size} height={size}>
  <use href={`/images/icons/sprite.svg#${id}`} />
</svg>