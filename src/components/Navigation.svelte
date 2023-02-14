<script>
    import {page} from '$app/stores';
    import {blur} from 'svelte/transition';

    let isOpen = false;
</script>

<nav>
    <ol class="desktop">
        <li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
            <a href="/">Home</a>
        </li>
        <li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
            <a href="/about">About</a>
        </li>
    </ol>

    <div class="mobile-button" on:click={() => (isOpen = true)}>Hamburger</div>

    {#if isOpen}
        <ol class="mobile-list" transition:blur={{ duration: 150 }}>
            <li
                    aria-current={$page.url.pathname === '/' ? 'page' : undefined}
                    on:click={() => (isOpen = !isOpen)}
            >
                <a href="/">Home</a>
            </li>
            <li
                    aria-current={$page.url.pathname === '/about' ? 'page' : undefined}
                    on:click={() => (isOpen = !isOpen)}
            >
                <a href="/about">About</a>
            </li>
        </ol>
    {/if}
</nav>

<style>
    nav {
    }

    .desktop {
        border: 1px solid black;
        list-style-type: none;
        margin: var(--baseLineGrid);
        padding: 0;
    }

    .mobile-button {
        display: none;
        border: 1px solid black;
    }

    .mobile-list {
        display: none;
    }

    @media only screen and (max-width: 800px) {

        nav {
            height: 2rem;
        }

        .desktop {
            display: none;
        }

        .mobile-button {
            display: flex;
        }

        .mobile-list {
            position: absolute;
            list-style-type: none;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: var(--baseLineGridS);
            left: 0;
            top: 0;
            width: 100%;
            height: 100vh;
            background: var(--bgColor);
            z-index: 10;
            margin: 0;
            padding: 0;
            transition: all ease-in 50ms;
        }
    }
</style>
