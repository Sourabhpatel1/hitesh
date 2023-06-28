<script lang="ts">
    import Hero from "$lib/components/Hero.svelte";
    import PageSection from "$lib/components/PageSection.svelte";

    let date = new Date().getFullYear()
</script>

<section class="page">
    <Hero/>
    <div class="info">
        <PageSection id={"products"} title={"Our Offerings"}>
            <ol>
                <li>All Varieties of Indian Major Carps & Gaza Fish in weights of above 500 grams.</li>
                <li>Prawns and Small Prawns grown in natural pond with high nutritional value.</li>
                <li>High Quality Seeds imported from top hatcheries in india of all varieties of Indian Major Carps and Gaza Fish.</li>
                <li>Timely Delivery Service is available for all of the above products offered by us.</li>
            </ol>
        </PageSection>
        <PageSection id={"services"} title={"Our Services"}>
            <ol>
                <li>Consultation for fish farmers.</li>
                <li>Consultation for fish seed production.</li>
                <li>Consultation for making new natural pond and improvement of old ponds</li>
                <li>Facilitation of medical services and medicines in case of medical emergencies</li>
            </ol>
        </PageSection>
        <PageSection id={"locations"} title={"Our Locations"}>
            <p>We have fish seed collection ponds and growing pond in :<br><br> Village - Katahardi, Post - Naurangpur, District - Raigarh, State - Chhattisgarh.</p>
        </PageSection>
        <PageSection id={"contact"} title={"Contact Us"}>
            <p>Mobile : +91 - 8839270533</p>
            <p>email : hp5019563@gmail.com</p>
        </PageSection>
    </div>
</section>
<div class="footer">
    <p>&copy;Hitesh Patel {date}</p>
</div>

<style>
    .page {
        display: flex;
        flex-direction: column;
        scroll-behavior: smooth !important;
    }
    .page .info {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        place-items: center;
        gap: 1rem;
    }
    ol {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    ol li {
        font-size: 1.5rem;
    }
    p {
        font-size: 1.5rem;
    }
    .footer {
        margin: 10px 0;
        min-height: 40px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    @media (max-width : 920px) {
        .page .info {
            display: flex;
            flex-direction: column;
        }
    }
</style>