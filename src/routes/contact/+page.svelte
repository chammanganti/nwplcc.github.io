<script>
  import { browser } from "$app/environment";
  import { enhance } from "$app/forms";
  import { page } from "$app/stores";

  export let form;

  let roleParam = "";
  let roleLabel = "";

  $: if (browser) {
    roleParam = $page.url.searchParams.get("role") ?? "";

    roleLabel =
      roleParam === "ops-manager"
        ? "Operations Manager"
        : roleParam === "supply-chain"
          ? "Supply Chain Manager"
          : "";
  }

  let submitting = false;
</script>

<svelte:head>
  <title>Contact — New World Project</title>
  <meta name="description" content="Get in touch with New World Project LLC." />
</svelte:head>

<section class="page-hero">
  <div class="page-hero-inner">
    <p class="eyebrow">Contact</p>
    <h1>Let's talk.</h1>
    <p class="sub">
      Use the form below and our team will get back to you as soon as possible.
    </p>
  </div>
</section>

<section class="contact-section">
  <div class="contact-inner">
    <div class="contact-aside">
      <div class="aside-block">
        <span class="aside-label">Based in</span>
        <span class="aside-value">Italy &amp; United States</span>
      </div>
      <div class="aside-block">
        <span class="aside-label">Specialization</span>
        <span class="aside-value">Acne Treatment &amp; Anti-Aging Skincare</span
        >
      </div>
      <div class="aside-block">
        <span class="aside-label">For careers</span>
        <span class="aside-value">
          <a href="/careers">View open roles →</a>
        </span>
      </div>
    </div>

    <div class="form-wrap">
      {#if form?.success}
        <div class="success-state">
          <div class="success-icon" aria-hidden="true">✓</div>
          <h2>Message received.</h2>
          <p>Thank you for reaching out. We'll be in touch shortly.</p>
          <a href="/" class="btn">Back to Home</a>
        </div>
      {:else}
        <form
          method="POST"
          use:enhance={() => {
            submitting = true;
            return async ({ update }) => {
              await update();
              submitting = false;
            };
          }}
        >
          {#if form?.error}
            <div class="form-error" role="alert">{form.error}</div>
          {/if}

          {#if roleLabel}
            <div class="role-banner">
              Applying for: <strong>{roleLabel}</strong>
              <input type="hidden" name="role" value={roleLabel} />
            </div>
          {/if}

          <div class="field">
            <label for="name">Name</label>
            <input
              type="text"
              id="name"
              name="name"
              required
              autocomplete="name"
              value={form?.values?.name ?? ""}
              placeholder="Your full name"
            />
          </div>

          <div class="field">
            <label for="email">Email</label>
            <input
              type="email"
              id="email"
              name="email"
              required
              autocomplete="email"
              value={form?.values?.email ?? ""}
              placeholder="you@example.com"
            />
          </div>

          <div class="field">
            <label for="message">Message</label>
            <textarea
              id="message"
              name="message"
              rows="6"
              required
              placeholder="How can we help?"
              >{form?.values?.message ?? ""}</textarea
            >
          </div>

          <button type="submit" class="btn" disabled={submitting}>
            {submitting ? "Sending…" : "Send Message"}
          </button>
        </form>
      {/if}
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
    margin-bottom: 1rem;
  }

  .sub {
    font-size: 1rem;
    line-height: 1.8;
    color: #666;
    font-weight: 300;
  }

  /* Contact layout */
  .contact-section {
    padding: 6rem 4rem;
  }

  .contact-inner {
    display: grid;
    grid-template-columns: 280px 1fr;
    gap: 6rem;
    max-width: 1000px;
    margin: 0 auto;
    align-items: start;
  }

  /* Aside */
  .aside-block {
    padding: 1.75rem 0;
    border-bottom: 1px solid #e8e6e1;
    display: flex;
    flex-direction: column;
    gap: 0.375rem;
  }

  .aside-block:first-child {
    border-top: 1px solid #e8e6e1;
  }

  .aside-label {
    font-size: 0.7rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #aaa;
  }

  .aside-value {
    font-size: 0.9375rem;
    color: #333;
    font-weight: 300;
    line-height: 1.5;
  }

  .aside-value a {
    color: #1a1a1a;
    text-decoration: underline;
    text-underline-offset: 3px;
    font-size: 0.875rem;
  }

  /* Form */
  .form-wrap {
    width: 100%;
  }

  .role-banner {
    background: #f5f3f0;
    border: 1px solid #e0dbd4;
    padding: 0.875rem 1.25rem;
    font-size: 0.875rem;
    color: #555;
    margin-bottom: 2rem;
    border-radius: 2px;
  }

  .role-banner strong {
    color: #1a1a1a;
    font-weight: 500;
  }

  .form-error {
    background: #fdf0f0;
    border: 1px solid #e8b4b4;
    color: #a03030;
    padding: 0.875rem 1.25rem;
    font-size: 0.875rem;
    margin-bottom: 1.5rem;
  }

  .field {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    margin-bottom: 1.75rem;
  }

  label {
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: #888;
  }

  input,
  textarea {
    font-family: "DM Sans", sans-serif;
    font-size: 0.9375rem;
    font-weight: 300;
    color: #1a1a1a;
    background: transparent;
    border: none;
    border-bottom: 1px solid #d0cdc8;
    padding: 0.625rem 0;
    outline: none;
    width: 100%;
    transition: border-color 0.2s;
    resize: vertical;
  }

  input::placeholder,
  textarea::placeholder {
    color: #bbb;
  }

  input:focus,
  textarea:focus {
    border-color: #1a1a1a;
  }

  .btn {
    display: inline-block;
    padding: 0.875rem 2.5rem;
    background: #003f7f;
    color: #faf9f7;
    font-family: "DM Sans", sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    border: 2px solid #003f7f;
    border-radius: 6rem;
    cursor: pointer;
    transition:
      background 0.25s,
      color 0.25s;
    margin-top: 0.5rem;
  }

  .btn:hover:not(:disabled) {
    background: transparent;
    color: #003f7f;
  }
  .btn:disabled {
    opacity: 0.5;
    cursor: not-allowed;
  }

  /* Success state */
  .success-state {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding: 4rem 0;
  }

  .success-icon {
    width: 3rem;
    height: 3rem;
    border: 1px solid #1a1a1a;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.25rem;
    color: #1a1a1a;
  }

  .success-state h2 {
    font-family: "Inter", serif;
    font-size: 2rem;
    font-weight: 300;
    color: #1a1a1a;
  }

  .success-state p {
    font-size: 0.9375rem;
    color: #666;
    font-weight: 300;
  }

  @media (max-width: 768px) {
    .page-hero {
      padding: 5rem 1.5rem 3rem;
    }
    .contact-section {
      padding: 4rem 1.5rem;
    }
    .contact-inner {
      grid-template-columns: 1fr;
      gap: 3rem;
    }
  }
</style>
