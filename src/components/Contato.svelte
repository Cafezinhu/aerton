<script lang="ts">
    export let href = "";
    export let text: string;
</script>
<div class="flex text-xs items-center mt-2">
    {#if href != ""}
        <a class="h-8 w-8 mr-2" href={href}>
            <slot />
        </a>
        <a class="link text-lg" href={href}>{text}</a>
    {:else}
        <div class="h-8 w-8 mr-2">
            <slot />
        </div>
        <p class="text-lg">{text}</p>
    {/if}
</div>