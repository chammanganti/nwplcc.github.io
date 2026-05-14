<script lang="ts">
    import bg from "$lib/assets/home-banner.jpg";
</script>

<svelte:head>
    <title>New World Project — Science-Backed Skincare</title>
    <meta
        name="description"
        content="A fast-growing skincare brand specializing in acne treatment and anti-aging solutions, founded in Italy, built for the US market."
    />
</svelte:head>

<section class="hero">
    <img src={bg} alt="" class="hero-bg" />

    <div class="hero-inner">
        <p class="eyebrow">Built for bold brands</p>
        <h1>NEW WORLD PROJECT LLC</h1>
        <p class="sub">
            High-performance products designed to improve confidence, skin,
            health, and everyday well-being.
        </p>
        <a href="/contact" class="btn">Contact Us</a>
    </div>
</section>

<section class="stats">
    <div class="stats-inner">
        {#each [["100,000+", "Women Served"], ["600+", "Influencer Collaborations"], ["10M", "Customer Goal by 2027"]] as [num, label]}
            <div class="stat">
                <span class="stat-num">{num}</span>
                <span class="stat-label">{label}</span>
            </div>
        {/each}
    </div>
</section>

<section class="pillars">
    <div class="section-header">
        <h2>What we stand for</h2>
        <p>
            A brand built on real results, honest science, and meaningful
            impact.
        </p>
    </div>
    <div class="pillars-grid">
        {#each [["Acne Treatment", "Clinically informed formulations targeting the root causes of breakouts — not just the surface."], ["Anti-Aging Solutions", "Products developed with leading dermatological expertise to address visible signs of aging effectively."], ["Real Impact", "We measure success by the confidence we restore, not just the products we sell."]] as [title, text]}
            <div class="pillar">
                <h3>{title}</h3>
                <p>{text}</p>
            </div>
        {/each}
    </div>
</section>

<section class="cta-band">
    <div class="cta-band-inner">
        <h2>Build something meaningful<br /><em>with us.</em></h2>
        <a href="/careers" class="btn btn-light">Discover Opportunities</a>
    </div>
</section>

<style>
    .hero {
        position: relative;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 6rem 4rem;
        overflow: hidden;
        text-align: center;
        background: #000;
    }

    .hero-bg {
        position: absolute;
        inset: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
        z-index: 0;
    }

    .hero::after {
        content: "";
        position: absolute;
        inset: 0;
        background: rgba(0, 0, 0, 0.55);
        z-index: 1;
    }

    .hero-inner {
        position: relative;
        z-index: 2;
        max-width: 720px;
    }

    @media (max-width: 768px) {
        .hero {
            min-height: 100vh;
            padding: 7rem 1.5rem 4rem;
        }

        .hero-bg {
            object-position: center;
        }
    }

    .eyebrow {
        font-size: 1rem;
        letter-spacing: 0.15em;
        text-transform: uppercase;
        color: #aaa;
        margin-bottom: 1.5rem;
    }

    h1 {
        font-family: "Inter", serif;
        font-size: clamp(2.75rem, 6vw, 5rem);
        font-weight: 600;
        line-height: 1.15;
        color: #fafafa;
        margin-bottom: 1.75rem;
    }

    .sub {
        font-size: 1.0625rem;
        line-height: 1.75;
        color: #eee;
        margin-bottom: 2.5rem;
        font-weight: 300;
    }

    .btn {
        display: inline-block;
        padding: 0.875rem 2.25rem;
        background: #003f7f;
        color: #faf9f7;
        font-size: 0.8rem;
        font-weight: 500;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        border: 2px solid #003f7f;
        border-radius: 6rem;
        transition:
            all 0.25s,
            color 0.25s;
    }

    .btn:hover {
        background: #fff;
        color: #003f7f;
        border-color: #fff;
    }

    .stats {
        padding: 4rem;
        border-top: 1px solid #e8e6e1;
        border-bottom: 1px solid #e8e6e1;
    }

    .stats-inner {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 2rem;
        max-width: 1100px;
        margin: 0 auto;
        text-align: center;
    }

    .stat {
        display: flex;
        flex-direction: column;
        gap: 0.375rem;
    }

    .stat-num {
        font-family: "Inter", serif;
        font-size: 2.75rem;
        font-weight: 300;
        color: #1a1a1a;
        line-height: 1;
    }

    .stat-label {
        font-size: 0.8rem;
        color: #888;
        letter-spacing: 0.06em;
        text-transform: uppercase;
    }

    /* Pillars */
    .pillars {
        padding: 7rem 4rem;
        max-width: 1200px;
        margin: 0 auto;
    }

    .section-header {
        margin-bottom: 4rem;
    }

    .section-header h2 {
        font-family: "Inter", serif;
        font-size: clamp(2rem, 3.5vw, 2.75rem);
        font-weight: 300;
        margin-bottom: 0.75rem;
    }

    .section-header p {
        color: #777;
        font-size: 1rem;
        font-weight: 300;
    }

    .pillars-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 2.5rem;
    }

    .pillar {
        padding: 2.5rem;
        border: 1px solid #e8e6e1;
        transition:
            border-color 0.25s,
            box-shadow 0.25s;
    }

    .pillar:hover {
        border-color: #003f7f;
        box-shadow: 0 4px 24px rgba(0, 0, 0, 0.05);
    }

    .pillar h3 {
        font-family: "Inter", serif;
        font-size: 1.375rem;
        font-weight: 400;
        margin-bottom: 1rem;
        color: #1a1a1a;
    }

    .pillar p {
        font-size: 0.9375rem;
        line-height: 1.7;
        color: #666;
        font-weight: 300;
    }

    /* CTA Band */
    .cta-band {
        background: #1a1a1a;
        padding: 6rem 4rem;
    }

    .cta-band-inner {
        max-width: 700px;
        margin: 0 auto;
        text-align: center;
    }

    .cta-band h2 {
        font-family: "Inter", serif;
        font-size: clamp(2rem, 4vw, 3.25rem);
        font-weight: 300;
        color: #faf9f7;
        margin-bottom: 2.5rem;
        line-height: 1.2;
    }

    .cta-band h2 em {
        font-style: italic;
        color: #c8b8a8;
    }

    .btn-light {
        background: transparent;
        color: #faf9f7;
        border-color: #faf9f7;
    }

    .btn-light:hover {
        background: #faf9f7;
        color: #1a1a1a;
    }

    @media (max-width: 1024px) {
        .stats-inner {
            grid-template-columns: repeat(2, 1fr);
        }
        .pillars-grid {
            grid-template-columns: 1fr 1fr;
        }
    }

    @media (max-width: 768px) {
        .hero {
            min-height: 100vh;
            padding: 4rem 1.5rem;
            background-position: center;
        }
        /* .hero { padding: 4rem 1.5rem; min-height: auto; } */
        /* .hero-deco { display: none; } */
        .stats {
            padding: 3rem 1.5rem;
        }
        .stats-inner {
            grid-template-columns: repeat(2, 1fr);
            gap: 2rem;
        }
        .pillars {
            padding: 4rem 1.5rem;
        }
        .pillars-grid {
            grid-template-columns: 1fr;
        }
        .cta-band {
            padding: 4rem 1.5rem;
        }
    }
</style>
