<script>
    import { onMount } from "svelte";
    export let component = "";

    let Thing;

    onMount(async () => {
        let components = await import.meta.globEager("./*.svelte");
        console.log(components);
        Thing = components[`./${component}.svelte`].default;
        console.log(Thing);
    });
</script>

<div>
    <svelte:component this={Thing} />
</div>
