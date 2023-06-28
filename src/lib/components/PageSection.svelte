<script lang="ts">
    export let id:string;
    export let title:string = "";
</script>

<section id={id}>
   <div class="title">
    <h4>{title}</h4>
   </div>
   <div class="content">
    <slot/>
   </div>
</section>

<style>
    section {
        min-width: 100%;
        min-height: 100%;
        margin: 1rem .5rem;
        padding: 1rem 1.5rem;
        display: flex;
        flex-direction: column;
        gap: 1rem;
        background: rgba(90, 79, 79, 0.2);
        border-radius: var(--radius-lg);
        box-shadow: 0 0 3px 3px rgba(0, 0, 0, 0.4);
        backdrop-filter: blur(10px);
        z-index: -1;
    }
    .title {
        text-align: center;
    }
    .content {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 0 2rem;
    }
</style>


