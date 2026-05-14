<script lang="ts">
  type Job = {
    id: string;
    title: string;
    type: string;
    location: string;
    description: string;
    formLink: string;
  };

  let activeJob: string = "";

  const jobs = [
    {
      id: "ops-manager",
      title: "Operations Manager",
      type: "Full-Time",
      location: "Remote",
      description:
        "Help drive the day-to-day execution of the business across teams, systems, and priorities. This role is ideal for someone highly organized, data-driven, and comfortable operating in a fast-moving environment where problem-solving and ownership matter.",
      formLink:
        "https://docs.google.com/forms/d/14QZ02OiB5FIT7VxlcNF00ilPIPX7voKyehvx8Frv61U/edit#responses",
    },
    {
      id: "supply-chain",
      title: "Supply Chain Manager",
      type: "Full-Time",
      location: "Remote / US",
      description:
        "Lead and optimize the flow of products from sourcing to delivery, ensuring operational efficiency and customer satisfaction. This role is ideal for someone with strong analytical skills, supply chain experience, and the ability to manage vendors, forecasting, and logistics with precision.",
      formLink:
        "https://docs.google.com/forms/d/1SAd6DkAeMLuwmYJkHogGgLIguwH5BLEuSsTiB4bAn6M/edit",
    },
  ];

  function toggleJob(id: string) {
    activeJob = activeJob === id ? "" : id;
  }
</script>

<svelte:head>
  <title>Careers — New World Project</title>
  <meta
    name="description"
    content="Join a fast-growing skincare brand with global ambitions. View open roles at New World Project LLC."
  />
</svelte:head>

<section class="page-hero">
  <div class="page-hero-inner">
    <p class="eyebrow">Careers</p>
    <h1>Build something<br /><em>that matters.</em></h1>
    <p class="sub">
      We are building a team of smart, driven people who want to grow fast, take
      ownership, and make a real difference. If you thrive in a high-performance
      environment and want to help scale a skincare brand with global ambitions,
      we’d love to hear from you.
    </p>
  </div>
</section>

<section class="values-strip">
  {#each ["Ownership", "High Performance", "Fast Growth", "Real Impact"] as value}
    <span>{value}</span>
  {/each}
</section>

<section class="openings">
  <div class="openings-inner">
    <div class="section-header">
      <h2>Open positions</h2>
      <p>{jobs.length} roles currently open</p>
    </div>

    <div class="jobs-list">
      {#each jobs as job}
        <div class="job-card" class:active={activeJob === job.id}>
          <button class="job-header" on:click={() => toggleJob(job.id)}>
            <div class="job-meta">
              <h3>{job.title}</h3>
              <div class="job-tags">
                <span class="tag">{job.type}</span>
                <span class="tag">{job.location}</span>
              </div>
            </div>
            <span class="job-toggle" aria-hidden="true"
              >{activeJob === job.id ? "−" : "+"}</span
            >
          </button>

          {#if activeJob === job.id}
            <div class="job-body">
              <p class="job-description">{job.description}</p>
              <a href={job.formLink} target="_blank" class="btn"
                >Apply for this role</a
              >
            </div>
          {/if}
        </div>
      {/each}
    </div>
  </div>
</section>

<section class="why">
  <div class="why-inner">
    <h2>Why New World Project LLC?</h2>
    <div class="why-grid">
      {#each [["Scale quickly", "We're growing fast. The work you do here has visible, direct impact on a brand serving tens of thousands of people."], ["Ownership culture", "No hand-holding. We hire smart people, give them real responsibility, and trust them to execute."], ["Learn from the best", "Work alongside a team that values continuous learning and invests in developing expertise at every level."]] as [title, text]}
        <div class="why-item">
          <h3>{title}</h3>
          <p>{text}</p>
        </div>
      {/each}
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
    margin-bottom: 1.5rem;
  }

  h1 em {
    font-style: italic;
    color: #5c4a3a;
  }

  .sub {
    font-size: 1rem;
    line-height: 1.8;
    color: #555;
    font-weight: 300;
    max-width: 580px;
  }

  /* Values strip */
  .values-strip {
    display: flex;
    gap: 0;
    border-bottom: 1px solid #e8e6e1;
    overflow-x: auto;
  }

  .values-strip span {
    flex: 1;
    padding: 1.25rem 2rem;
    font-size: 0.75rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #888;
    text-align: center;
    border-right: 1px solid #e8e6e1;
    white-space: nowrap;
  }

  .values-strip span:last-child {
    border-right: none;
  }

  /* Openings */
  .openings {
    padding: 6rem 4rem;
  }

  .openings-inner {
    max-width: 900px;
    margin: 0 auto;
  }

  .section-header {
    margin-bottom: 3rem;
  }

  .section-header h2 {
    font-family: "Inter", serif;
    font-size: clamp(1.75rem, 3vw, 2.5rem);
    font-weight: 300;
    margin-bottom: 0.375rem;
  }

  .section-header p {
    color: #888;
    font-size: 0.875rem;
    font-weight: 300;
  }

  .jobs-list {
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .job-card {
    border: 1px solid #e8e6e1;
    margin-bottom: -1px;
    transition: border-color 0.2s;
  }

  .job-card.active {
    border-color: #003f7f;
    z-index: 1;
    position: relative;
  }

  .job-header {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 2rem 2.5rem;
    background: none;
    border: none;
    cursor: pointer;
    text-align: left;
    gap: 1rem;
    transition: background 0.2s;
  }

  .job-header:hover {
    background: #f5f3f0;
  }

  .job-card.active .job-header {
    background: #f5f3f0;
  }

  .job-meta h3 {
    font-family: "Inter", serif;
    font-size: 1.375rem;
    font-weight: 400;
    color: #1a1a1a;
    margin-bottom: 0.5rem;
  }

  .job-tags {
    display: flex;
    gap: 0.5rem;
  }

  .tag {
    font-size: 0.7rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: #888;
    border: 1px solid #ddd;
    padding: 0.25rem 0.625rem;
  }

  .job-toggle {
    font-size: 1.5rem;
    color: #999;
    line-height: 1;
    flex-shrink: 0;
    font-family: "Inter", serif;
  }

  .job-body {
    padding: 0 2.5rem 2.5rem;
  }

  .job-description {
    font-size: 0.9375rem;
    line-height: 1.8;
    color: #555;
    font-weight: 300;
    margin-bottom: 2.5rem;
    padding-bottom: 2rem;
    border-bottom: 1px solid #e8e6e1;
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
      background 0.25s,
      color 0.25s;
  }

  .btn:hover {
    background: transparent;
    color: #003f7f;
    border-color: #003f7f;
  }

  /* Why section */
  .why {
    padding: 6rem 4rem;
    background: #1a1a1a;
    border-top: 1px solid #e8e6e1;
  }

  .why-inner {
    max-width: 1100px;
    margin: 0 auto;
  }

  .why h2 {
    font-family: "Inter", serif;
    font-size: clamp(1.75rem, 3vw, 2.5rem);
    font-weight: 300;
    color: #faf9f7;
    margin-bottom: 3.5rem;
  }

  .why-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 3rem;
  }

  .why-item h3 {
    font-family: "Inter", serif;
    font-size: 1.25rem;
    font-weight: 400;
    color: #c8b8a8;
    margin-bottom: 0.75rem;
  }

  .why-item p {
    font-size: 0.9rem;
    line-height: 1.75;
    color: #888;
    font-weight: 300;
  }

  @media (max-width: 768px) {
    .page-hero {
      padding: 5rem 1.5rem 3rem;
    }
    .openings {
      padding: 4rem 1.5rem;
    }
    .job-header {
      padding: 1.5rem;
    }
    .job-body {
      padding: 0 1.5rem 1.5rem;
    }
    .why {
      padding: 4rem 1.5rem;
    }
    .why-grid {
      grid-template-columns: 1fr;
      gap: 2rem;
    }
  }
</style>
