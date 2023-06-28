<script lang="ts">
    import vid from '$lib/assets/production_id 3824575 (1080p).mp4'
    import { goto } from '$app/navigation';
</script>

<section class="hero">
    <div class="video-container">
        <video src="{vid}" muted autoplay loop></video>
    </div>
    <div class="content">
        <h1>Hitesh Patel</h1>
        <h3>Fisheries and Aquaculture</h3>
        <button class="cta" on:click={()=>{goto("#products")}}>Lean More</button>
    </div>
</section>

<style>
    .hero {
        position: relative;
        min-height: 85vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 0 20px;
        z-index: 1;
    }
    .video-container {
        position: absolute;
        inset: 0;
        overflow: hidden;
        background: transparent;
    }
    .video-container::after {
        content: '';
        position: absolute;
        inset: 0;
        background: rgba(0, 0, 0, .4);
        backdrop-filter: blur(3px);
    }
    .video-container video {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        object-fit: cover;
        pointer-events: none;
    }
    .content {
        max-width: 800px;
        max-height: 600px;
        padding: 1rem;
        display: flex;
        flex-direction: column;
        z-index: 1;
        text-align:center;
    }
    .content h1,
    .content h3 {
        color: var(--cosmic-latte);
    }
    .content .cta {
        margin: 20px 0;
        height: 40px;
        background: var(--ebony);
        border-radius: var(--radius-lg);
        box-shadow: 0 0 3px 3px rgba(0, 0, 0, .4);
        z-index: 10;
        transition: scale .2s ease;
        transition: background .5s ease;
        transition: color .5s ease;
        cursor: pointer;
    }
    .content .cta:hover,
    .content .cta:focus-visible {
        color: black;
        background: var(--cosmic-latte);
    }
    .content .cta:active {
        transform: scale(.98);
    }
</style>