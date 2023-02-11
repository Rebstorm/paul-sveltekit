<script lang="ts">

    const year = new Date().getFullYear();

</script>

<footer>
    &copy; Paul Jacks {year}
</footer>


<style>
    footer {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: var(--baseLineGrid);
    }

    footer a {
        font-weight: bold;
    }

    @media (min-width: 480px) {
        footer {
            padding: var(--baseLineGrid)
        }
    }
</style>