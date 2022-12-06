<script>
    import { page } from '$app/stores';

</script>

<nav>
    <ul>
        <li aria-current={$page.url.pathname === '/' ? 'home' : undefined}>
            <a href="/about">Help</a>
        </li>
        <li aria-current={$page.url.pathname === '/about' ? 'about' : undefined}>
            <a href="/about">Phone</a>
        </li>
        <li aria-current={$page.url.pathname === '/about' ? 'about' : undefined}>
            <a href="/about">Games</a>
        </li>
    </ul>
</nav>


<style>
    ul {
        display: flex;
        justify-content: space-around;
        padding-inline: 3em;
        padding-top: 1em;

        font-size: 54px;
    }
    li {
        border-bottom: 3px solid var(--color-offblack);
        border-top: 3px solid var(--color-offblack);
        padding: 0.5em;

        transition: 1s;
        background: linear-gradient(#3C6E71,#3C6E71) no-repeat, var(--color-offwhite);
        background-size: 100% 0;
        background-position: center;
    }
    li:hover {
        background-size: 100% 100%
    }
    a {
        text-decoration: none;
        color: var(--color-offblack);

    }
</style>
