<script>
    import Header from '../components/Header.svelte';
    import Footer from '../components/Footer.svelte';
    import Navigation from '../components/Navigation.svelte';
    import './styles.css';
</script>

<div class="app">
    <Header/>

    <main>
        <Navigation/>
        <slot/>
    </main>

    <Footer/>


</div>

<style>
    .app {
        display: flex;
        flex-direction: column;
        min-height: 100vh;
    }

    main {
        background: var(--tertiaryColor);
        flex: 1;
        display: flex;
        flex-direction: row;
        gap: var(--baseLineGrid);
        padding: 1rem;
        width: 100%;
        margin: 0 auto;
        box-sizing: border-box;
        border: 1px solid black;
    }


    /* Phones,s lightly different layout. */
    @media only screen and (max-width: 390px) {
        :root {
            --baseLineGrid: 4rem;
            --baseLineGridS: 2rem;
            overflowX: hidden;
        }
    }
</style>
