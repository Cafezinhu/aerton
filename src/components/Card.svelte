<script lang="ts">
    export let img: string;
    export let title: string;
    export let description: string;
</script>

<div class="card bg-base-200 flex-1">
    <figure><img class="w-full lg:h-44" src={img} alt=""></figure>
    <div class="card-body">
        <h2 class="card-title">{title}</h2>
        <p>{description}</p>
    </div>
</div>