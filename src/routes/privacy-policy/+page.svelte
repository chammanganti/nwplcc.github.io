<svelte:head>
  <title>Privacy Policy — New World Project</title>
  <meta
    name="description"
    content="Privacy Policy for New World Project LLC. Learn how we collect and use your information."
  />
</svelte:head>

<section class="page-hero">
  <div class="page-hero-inner">
    <p class="eyebrow">Legal</p>
    <h1>Privacy Policy</h1>
    <p class="sub">
      Last updated: May 21, 2025. This policy explains what information we collect,
      how we use it, and your rights regarding that information.
    </p>
  </div>
</section>

<section class="policy-section">
  <div class="policy-inner">
    <aside class="policy-nav">
      <p class="nav-label">On this page</p>
      <ul>
        <li><a href="#overview">Overview</a></li>
        <li><a href="#collection">Information We Collect</a></li>
        <li><a href="#use">How We Use It</a></li>
        <li><a href="#sharing">Sharing & Disclosure</a></li>
        <li><a href="#retention">Data Retention</a></li>
        <li><a href="#rights">Your Rights</a></li>
        <li><a href="#contact">Contact Us</a></li>
      </ul>
    </aside>

    <div class="policy-body">
      <div class="policy-block" id="overview">
        <h2>Overview</h2>
        <p>
          New World Project LLC ("we", "us", or "our") is committed to
          protecting your personal information. This Privacy Policy applies to
          information collected through our website, including our contact form
          and job application process.
        </p>
        <p>
          We collect only what is necessary, we do not sell your data, and we
          will never use it for purposes beyond what is described here.
        </p>
      </div>

      <div class="policy-block" id="collection">
        <h2>Information We Collect</h2>
        <p>We collect personal information through two points of contact:</p>

        <div class="info-card">
          <span class="info-card-label">Contact Form</span>
          <p>
            When you submit our contact form, we collect your <strong
              >name</strong
            >, <strong>email address</strong>, and the
            <strong>message</strong> you provide. This information is transmitted
            securely to us via Web3Forms.
          </p>
        </div>

        <div class="info-card">
          <span class="info-card-label">Job Applications</span>
          <p>
            When you apply for a role, you are redirected to a Google Form
            hosted by Google LLC. Any information you submit there — which may
            include your name, email, work history, and other application
            details — is collected and stored by Google in accordance with
            <a
              href="https://policies.google.com/privacy"
              target="_blank"
              rel="noopener noreferrer">Google's Privacy Policy</a
            >.
          </p>
        </div>

        <p>
          We do not use cookies, tracking pixels, or analytics tools on this
          website, and we do not collect any information passively.
        </p>
      </div>

      <div class="policy-block" id="use">
        <h2>How We Use It</h2>
        <p>Information collected through our contact form is used solely to:</p>
        <ul>
          <li>Respond to your inquiry or message</li>
          <li>Follow up on matters you have raised with us</li>
        </ul>
        <p>
          Information submitted through job applications is used solely for
          evaluating your candidacy for the role you applied to.
        </p>
        <p>
          We do not use your information for marketing, profiling, or any
          automated decision-making.
        </p>
      </div>

      <div class="policy-block" id="sharing">
        <h2>Sharing &amp; Disclosure</h2>
        <p>
          We do not sell, rent, or trade your personal information. We may share
          it only in the following limited circumstances:
        </p>
        <ul>
          <li>
            <strong>Service providers</strong> — Web3Forms processes contact form
            submissions on our behalf. Google LLC processes job application data
            through Google Forms.
          </li>
          <li>
            <strong>Legal obligations</strong> — If required by law or to protect
            the rights and safety of our users or the public.
          </li>
        </ul>
        <p>
          Both Web3Forms and Google operate under their own privacy policies and
          security standards. We encourage you to review them.
        </p>
      </div>

      <div class="policy-block" id="retention">
        <h2>Data Retention</h2>
        <p>
          Contact form submissions are retained only as long as necessary to
          address your inquiry, after which they are deleted from our records.
        </p>
        <p>
          Job application data stored in Google Forms is retained for a
          reasonable period following the close of a hiring cycle, then deleted.
          Google may retain metadata in accordance with their own policies.
        </p>
      </div>

      <div class="policy-block" id="rights">
        <h2>Your Rights</h2>
        <p>
          Depending on your location, you may have rights regarding your
          personal data, including the right to access, correct, or request
          deletion of information we hold about you.
        </p>
        <p>
          To exercise any of these rights, please reach out to us directly using
          the contact information below. We will respond within a reasonable
          timeframe.
        </p>
      </div>

      <div class="policy-block" id="contact">
        <h2>Contact Us</h2>
        <p>
          If you have any questions about this Privacy Policy or how your data
          is handled, please contact us through our <a href="/contact"
            >contact page</a
          >.
        </p>
        <p class="muted">
          We may update this policy from time to time. Any changes will be
          reflected on this page with a revised date at the top.
        </p>
      </div>
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

  /* Layout */
  .policy-section {
    padding: 6rem 4rem;
  }

  .policy-inner {
    display: grid;
    grid-template-columns: 220px 1fr;
    gap: 6rem;
    max-width: 1000px;
    margin: 0 auto;
    align-items: start;
  }

  /* Sidebar nav */
  .policy-nav {
    position: sticky;
    top: 7rem;
  }

  .nav-label {
    font-size: 0.7rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #aaa;
    margin-bottom: 1rem;
  }

  .policy-nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
    border-left: 1px solid #e8e6e1;
  }

  .policy-nav ul li a {
    display: block;
    padding: 0.5rem 1rem;
    font-size: 0.875rem;
    color: #888;
    font-weight: 300;
    text-decoration: none;
    transition: color 0.2s;
  }

  .policy-nav ul li a:hover {
    color: #1a1a1a;
  }

  /* Body */
  .policy-body {
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .policy-block {
    padding: 3rem 0;
    border-bottom: 1px solid #e8e6e1;
    scroll-margin-top: 7rem;
  }

  .policy-block:first-child {
    padding-top: 0;
  }

  .policy-block:last-child {
    border-bottom: none;
  }

  .policy-block h2 {
    font-family: "Inter", serif;
    font-size: 1.375rem;
    font-weight: 400;
    color: #1a1a1a;
    margin-bottom: 1.25rem;
  }

  .policy-block p {
    font-size: 0.9375rem;
    line-height: 1.85;
    color: #555;
    font-weight: 300;
    margin-bottom: 1rem;
  }

  .policy-block p:last-child {
    margin-bottom: 0;
  }

  .policy-block ul {
    margin: 0.75rem 0 1rem 0;
    padding-left: 1.25rem;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .policy-block ul li {
    font-size: 0.9375rem;
    line-height: 1.75;
    color: #555;
    font-weight: 300;
  }

  .policy-block a {
    color: #1a1a1a;
    text-decoration: underline;
    text-underline-offset: 3px;
  }

  /* Info cards */
  .info-card {
    background: #f5f3f0;
    border: 1px solid #e8e6e1;
    padding: 1.5rem 1.75rem;
    margin: 1.25rem 0;
  }

  .info-card-label {
    display: block;
    font-size: 0.7rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #aaa;
    margin-bottom: 0.625rem;
  }

  .info-card p {
    margin-bottom: 0;
  }

  .muted {
    color: #999 !important;
    font-size: 0.875rem !important;
  }

  @media (max-width: 768px) {
    .page-hero {
      padding: 5rem 1.5rem 3rem;
    }

    .policy-section {
      padding: 4rem 1.5rem;
    }

    .policy-inner {
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .policy-nav {
      position: static;
      padding-bottom: 2rem;
      border-bottom: 1px solid #e8e6e1;
    }
  }
</style>
