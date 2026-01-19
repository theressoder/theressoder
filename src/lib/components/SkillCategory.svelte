<script lang="ts">
    export let title: string;
    export let skills: string[] = [];
</script>

<div>
    <div class="flex items-center space-x-3 mb-6">
        <div class="p-2 bg-ink text-paper rounded-lg">
            <slot name="icon" />
        </div>
        <h3 class="text-xl font-bold">{title}</h3>
    </div>
    <div class="flex flex-wrap gap-2">
        {#each skills as skill}
            <span class="px-3 py-1 bg-white border border-ink/10 text-ink/80 text-sm rounded-full hover:border-accent hover:text-ink transition-colors cursor-default">
                {skill}
            </span>
        {/each}
    </div>
</div>