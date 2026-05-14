<script>
    import { page } from "$app/stores";
    import { onMount } from "svelte";
    import logo from "$lib/assets/logo.png";

    let scrolled = false;
    let menuOpen = false;

    onMount(() => {
        const handler = () => {
            scrolled = window.scrollY > 20;
        };
        window.addEventListener("scroll", handler);
        return () => window.removeEventListener("scroll", handler);
    });

    $: isHome = $page.url.pathname === "/";
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link
        rel="preconnect"
        href="https://fonts.gstatic.com"
        crossorigin="anonymous"
    />
    <link
        href="https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=DM+Sans:wght@300;400;500&display=swap"
        rel="stylesheet"
    />
</svelte:head>

<nav
    class:transparent={isHome && !scrolled && !menuOpen}
    class:scrolled={scrolled || !isHome || menuOpen}
>
    <a href="/" class="logo">
        <img src={logo} alt="New World Project LLC" class="logo-mark" />
        <span class="logo-text">New World Project LLC</span>
    </a>

    <button
        class="burger"
        on:click={() => (menuOpen = !menuOpen)}
        aria-label="Toggle menu"
    >
        <span class:open={menuOpen}></span>
        <span class:open={menuOpen}></span>
    </button>

    <ul class="desktop-nav">
        {#each [["/", "Home"], ["/about", "About"], ["/careers", "Careers"], ["/contact", "Contact"]] as [href, label]}
            <li>
                <a
                    {href}
                    class:active={$page.url.pathname === href}
                    on:click={() => (menuOpen = false)}
                >
                    {label}
                </a>
            </li>
        {/each}
    </ul>
</nav>
<ul class="mobile-nav" class:open={menuOpen}>
    {#each [["/", "Home"], ["/about", "About"], ["/careers", "Careers"], ["/contact", "Contact"]] as [href, label]}
        <li>
            <a
                {href}
                class:active={$page.url.pathname === href}
                on:click={() => (menuOpen = false)}
            >
                {label}
            </a>
        </li>
    {/each}
</ul>

<main>
    <slot />
</main>

<footer>
    <div class="footer-inner">
        <span class="footer-brand"></span>
        <span class="footer-copy"
            >© {new Date().getFullYear()} New World Project LLC. All rights reserved.</span
        >
    </div>
</footer>

<style>
    :global(*, *::before, *::after) {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    :global(html) {
        font-family: "Inter", sans-serif;
        font-size: 16px;
        color: #1a1a1a;
        background: #faf9f7;
        scroll-behavior: smooth;
    }

    :global(body) {
        min-height: 100vh;
    }

    :global(a) {
        text-decoration: none;
        color: inherit;
    }

    nav {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        z-index: 100;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: rgba(0, 0, 0, 1);
        padding: 2rem 4rem;
        transition:
            background 0.3s,
            box-shadow 0.3s,
            padding 0.3s;
        z-index: 100;
    }

    nav.scrolled {
        background-color: rgba(0, 0, 0, 0.9);
        backdrop-filter: blur(12px);
        box-shadow: 0 1px 0 rgba(0, 0, 0, 0.2);
    }

    nav.transparent {
        background-color: transparent;
        box-shadow: none;
        backdrop-filter: none;
    }

    .mobile-nav {
        position: fixed;
        inset: 0;

        margin: 0;
        padding: 0;
        list-style: none;

        display: none;
        flex-direction: column;
        align-items: center;
        justify-content: center;

        background: rgba(0, 0, 0, 0.96);
    }

    .logo {
        display: flex;
        align-items: center;
        gap: 0.85rem;

        font-family: "Inter", serif;
        font-size: 1.05rem;
        font-weight: 400;
        letter-spacing: 0.04em;
        color: #fafafa;
    }

    .logo-mark {
        width: 42px;
        height: 42px;
        object-fit: contain;
        flex-shrink: 0;
    }

    .logo-text {
        white-space: nowrap;
    }

    @media (max-width: 768px) {
        .mobile-nav {
            position: fixed;
            inset: 0;

            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;

            background: rgba(0, 0, 0, 0.96);

            opacity: 0;
            pointer-events: none;
            transition: opacity 0.25s ease;
        }

        .mobile-nav.open {
            opacity: 1;
            pointer-events: auto;
        }
    }

    .logo {
        font-family: "Inter", serif;
        font-size: 1.05rem;
        font-weight: 400;
        letter-spacing: 0.04em;
        color: #fafafa;
    }

    .logo-mark {
        width: 36px;
        height: 36px;
    }

    ul {
        display: flex;
        gap: 2.5rem;
        list-style: none;
    }

    ul a {
        font-size: 0.8125rem;
        font-weight: 400;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: #fafafa;
        transition: color 0.2s;
        position: relative;
    }

    ul a::after {
        content: "";
        position: absolute;
        bottom: -2px;
        left: 0;
        right: 0;
        height: 1px;
        background: #fafafa;
        transform: scaleX(0);
        transition: transform 0.25s;
    }

    ul a:hover,
    ul a.active {
        color: #fafafa;
    }
    ul a:hover::after,
    ul a.active::after {
        transform: scaleX(1);
    }

    .burger {
        display: none;
    }

    main {
        min-height: calc(100vh - 140px);
    }

    footer {
        border-top: 1px solid #e8e6e1;
        padding: 3rem 4rem;
    }

    .footer-inner {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 1rem;
        flex-wrap: wrap;
    }

    .footer-brand {
        font-family: "Inter", serif;
        font-size: 1rem;
        font-weight: 500;
    }

    .footer-copy {
        font-size: 0.75rem;
        color: #aaa;
        letter-spacing: 0.04em;
    }

    @media (max-width: 768px) {
        nav {
            padding: 1.25rem 1.5rem;
        }
        nav.scrolled {
            padding: 1rem 1.5rem;
        }

        .burger {
            display: flex;
            flex-direction: column;
            gap: 5px;
            background: none;
            border: none;
            cursor: pointer;
            padding: 4px;
        }

        .burger span {
            display: block;
            width: 22px;
            height: 1.5px;
            background: #fafafa;
            transition:
                transform 0.25s,
                opacity 0.25s;
        }

        .burger span:first-child.open {
            transform: translateY(6.5px) rotate(45deg);
        }
        .burger span:last-child.open {
            transform: translateY(-6.5px) rotate(-45deg);
        }

        ul {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;

            background: rgba(0, 0, 0, 0.96);
            backdrop-filter: blur(16px);

            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 2.5rem;
            z-index: 99;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.25s ease;
        }

        ul.open {
            display: flex;
            opacity: 1;
            pointer-events: auto;
        }
        ul a {
            font-size: 1rem;
        }

        footer {
            padding: 2rem 1.5rem;
        }
        .footer-inner {
            flex-direction: column;
            align-items: flex-start;
            gap: 0.5rem;
        }
    }
</style>
