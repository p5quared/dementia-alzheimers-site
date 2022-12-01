<script>
    import map from "$lib/images/google_maps.webp";
</script>


<div class="wrapper">
    <h1>Here is your next appointment:</h1>
    <div id="body">
        <div id="directions">
            <img src={map} alt="google maps">
            <p>Click for Directions</p>
        </div>
        <div id="information">
            <ul>
                <li>
                    -Tomorrow, February 29, 2023 @10AM
                </li>
                <li>
                    -Annual Checkup
                </li>
                <li>
                    -Dr. Van Nostrand
                </li>
                <li>
                    -Belle Haven Medical Center<br>
                    Address Address, NY 11111
                </li>
            </ul>
            <a href="/">Return</a>
        </div>
    </div>
</div>

<style>
    .wrapper {
        background-color: #3C6E71;
        color: var(--color-offwhite);
        padding: 3em;
    }
    #body {
        display: flex;
        gap: 2em;
        height: 100vh;
        padding-top: 3em;
    }
    #information {
        background-color: #284b63;
        padding: 1em;
        font-size: 32px;
        height: 360px;
    }
    a {
        padding: 0.25em 0.5em;
        background-color: #3C6E71;
        color: var(--color-offwhite);
        border: solid black;

    }
    li {
        padding-top: 1em;
    }
    ul {
        padding-bottom: 0.75em;
    }
    img {
        width: 800px;
    }
    h1 {
        font-size: 54px;
    }
</style>

