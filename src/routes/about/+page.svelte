<svelte:head>
    <title>About — New World Project</title>
    <meta
        name="description"
        content="The story behind New World Project LLC — founded in Italy from a personal battle with acne, now serving over 100,000 women in the US."
    />
</svelte:head>

<section class="page-hero">
    <div class="page-hero-inner">
        <p class="eyebrow">Our Story</p>
        <h1>Skincare designed for<br /><em>real, lasting results.</em></h1>
    </div>
</section>

<section class="story">
    <div class="story-inner">
        <div class="story-text">
            <h2>How we started</h2>
            <p>
                Founded in Italy, we are a fast-growing skincare brand
                specializing in acne treatment and anti-aging solutions, now
                operating primarily in the US market.
            </p>
            <p>
                The brand was born from the founder’s personal struggle with
                acne and was built to create effective skincare solutions that
                genuinely improve people’s lives.
            </p>
            <p>
                We have helped improve the skin of over 100,000 women,
                collaborated with more than 600 influencers, and partnered with
                a celebrity doctor who is the face of our marketing campaigns.
            </p>
        </div>
        <div class="story-aside">
            <div class="aside-stat">
                <span class="big-num">100K+</span>
                <span>Women who've trusted our products</span>
            </div>
            <div class="aside-stat">
                <span class="big-num">600+</span>
                <span>Influencer partnerships built</span>
            </div>
        </div>
    </div>
</section>

<section class="mission-vision">
    <div class="mv-grid">
        <div class="mv-card">
            <span class="mv-label">Mission</span>
            <p>
                Our mission is to improve lives through high-quality skincare
                solutions that address real concerns such as acne and aging,
                while building a brand that combines innovation, trust, and
                performance.
            </p>
        </div>
        <div class="mv-card mv-card--dark">
            <span class="mv-label">Vision</span>
            <p>
                Our goal is to reach 10 million customers in the next 3 years
                and become a category leader in results-driven skincare.
            </p>
        </div>
    </div>
</section>

<section class="values">
    <div class="values-inner">
        <div class="section-header">
            <h2>What guides us</h2>
            <p>The principles behind every decision we make.</p>
        </div>
        <div class="values-grid">
            {#each [["01", "Continuous Learning", "We seek knowledge from the best minds in skincare, dermatology, and business — always improving."], ["02", "Open Communication", "Honest, direct dialogue across every level of the team. No politics, no noise."], ["03", "Data-Driven Decisions", "We trust evidence over instinct and measure what matters to our customers and the business."], ["04", "High Standards", "We hold ourselves accountable to excellence — in formulation, in execution, in every touchpoint."], ["05", "Fast Execution", "Speed matters. We move decisively without sacrificing quality or care."], ["06", "Real Impact", "We measure success by the confidence we restore and the lives we genuinely improve."]] as [num, title, text]}
                <div class="value-item">
                    <span class="value-num">{num}</span>
                    <div>
                        <h3>{title}</h3>
                        <p>{text}</p>
                    </div>
                </div>
            {/each}
        </div>
    </div>
</section>

<section class="culture">
    <div class="culture-inner">
        <div class="culture-text">
            <h2>Our culture</h2>
            <p>
                We are a growing, fast-paced company with a strong presence in
                the US and Europe. Our culture is built around performance,
                ownership, and learning — with the opportunity to contribute
                meaningfully to a brand that is scaling quickly.
            </p>
            <p>
                We're not a slow-moving corporation. We're a team of sharp,
                driven people who care deeply about results and about each
                other.
            </p>
            <a href="/careers" class="btn">See Open Roles</a>
        </div>
    </div>
</section>

<style>
    .page-hero {
        padding: 8rem 4rem 5rem;
        border-bottom: 1px solid #e8e6e1;
    }

    .page-hero-inner {
        max-width: 700px;
    }

    .eyebrow {
        font-size: 0.75rem;
        letter-spacing: 0.15em;
        text-transform: uppercase;
        color: #888;
        margin-bottom: 1.5rem;
    }

    h1 {
        font-family: "Inter", serif;
        font-size: clamp(2.5rem, 5vw, 4.25rem);
        font-weight: 300;
        line-height: 1.15;
        color: #1a1a1a;
    }

    h1 em{
        font-style: italic;
        color: #5c4a3a;
    }

    /* Story */
    .story {
        padding: 6rem 4rem;
        border-bottom: 1px solid #e8e6e1;
    }

    .story-inner {
        display: grid;
        grid-template-columns: 1fr 340px;
        gap: 6rem;
        max-width: 1100px;
        margin: 0 auto;
        align-items: start;
    }

    .story-text h2 {
        font-family: "Inter", serif;
        font-size: 1.875rem;
        font-weight: 300;
        margin-bottom: 1.5rem;
        color: #1a1a1a;
    }

    .story-text p {
        font-size: 1rem;
        line-height: 1.85;
        color: #555;
        font-weight: 300;
        margin-bottom: 1.25rem;
    }

    .aside-stat {
        padding: 2rem 0;
        border-bottom: 1px solid #e8e6e1;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }

    .aside-stat:last-child {
        border-bottom: none;
    }

    .big-num {
        font-family: "Inter", serif;
        font-size: 3rem;
        font-weight: 300;
        line-height: 1;
        color: #1a1a1a;
    }

    .aside-stat span:last-child {
        font-size: 0.8125rem;
        color: #888;
        text-transform: uppercase;
        letter-spacing: 0.08em;
    }

    .mv-grid {
        display: grid;
        grid-template-columns: 1fr 1fr;
    }

    .mv-card {
        padding: 5rem 4rem;
        border-top: 1px solid #e8e6e1;
    }

    .mv-card--dark {
        background: #1a1a1a;
        border-color: #1a1a1a;
    }

    .mv-label {
        display: block;
        font-size: 0.75rem;
        letter-spacing: 0.15em;
        text-transform: uppercase;
        margin-bottom: 1.5rem;
        color: #888;
    }

    .mv-card--dark .mv-label {
        color: #666;
    }

    .mv-card p {
        font-family: "Inter", serif;
        font-size: 1.5rem;
        font-weight: 300;
        line-height: 1.65;
        color: #2a2a2a;
    }

    .mv-card--dark p {
        color: #d8cfc6;
    }

    /* Values */
    .values {
        padding: 6rem 4rem;
        border-top: 1px solid #e8e6e1;
    }

    .values-inner {
        max-width: 1100px;
        margin: 0 auto;
    }

    .section-header {
        margin-bottom: 4rem;
    }

    .section-header h2 {
        font-family: "Inter", serif;
        font-size: clamp(1.75rem, 3vw, 2.5rem);
        font-weight: 300;
        margin-bottom: 0.5rem;
    }

    .section-header p {
        color: #888;
        font-weight: 300;
        font-size: 0.9375rem;
    }

    .values-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 0;
        border-top: 1px solid #e8e6e1;
        border-left: 1px solid #e8e6e1;
    }

    .value-item {
        padding: 2.5rem;
        border-right: 1px solid #e8e6e1;
        border-bottom: 1px solid #e8e6e1;
        display: flex;
        gap: 1.25rem;
        align-items: flex-start;
        transition: background 0.2s;
    }

    .value-item:hover {
        background: #f5f3f0;
    }

    .value-num {
        font-family: "Inter", serif;
        font-size: 0.875rem;
        color: #bbb;
        flex-shrink: 0;
        margin-top: 0.2rem;
    }

    .value-item h3 {
        font-family: "Inter", serif;
        font-size: 1.125rem;
        font-weight: 400;
        color: #1a1a1a;
        margin-bottom: 0.5rem;
    }

    .value-item p {
        font-size: 0.875rem;
        line-height: 1.65;
        color: #777;
        font-weight: 300;
    }

    /* Culture */
    .culture {
        padding: 6rem 4rem;
        border-top: 1px solid #e8e6e1;
        background: #f5f3f0;
    }

    .culture-inner {
        max-width: 700px;
    }

    .culture-text h2 {
        font-family: "Inter", serif;
        font-size: clamp(1.75rem, 3vw, 2.5rem);
        font-weight: 300;
        margin-bottom: 1.5rem;
    }

    .culture-text p {
        font-size: 1rem;
        line-height: 1.8;
        color: #555;
        font-weight: 300;
        margin-bottom: 1.25rem;
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
        background: transparent;
        color: #003f7f;
        border-color: #003f7f;
    }

    @media (max-width: 1024px) {
        .values-grid {
            grid-template-columns: repeat(2, 1fr);
        }
    }

    @media (max-width: 768px) {
        .page-hero {
            padding: 5rem 1.5rem 3rem;
        }
        .story {
            padding: 4rem 1.5rem;
        }
        .story-inner {
            grid-template-columns: 1fr;
            gap: 3rem;
        }
        .mv-grid {
            grid-template-columns: 1fr;
        }
        .mv-card {
            padding: 3rem 1.5rem;
        }
        .values {
            padding: 4rem 1.5rem;
        }
        .values-grid {
            grid-template-columns: 1fr;
        }
        .culture {
            padding: 4rem 1.5rem;
        }
    }
</style>
