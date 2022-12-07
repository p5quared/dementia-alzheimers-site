<script>
    import * as aList from "./data/alist.json";
    import Game from "./game.svelte";
    const data = aList.data.map(item => {
        item.img = `images/${item.img}`
        return item;
    });

    let videoSource = null;
    let loading = false;
    let loaded = false;
    const videoCamera = async () => {
        try {
            loading = true;
            videoSource.srcObject = await navigator.mediaDevices.getUserMedia({
                video: true,
            });
            videoSource.play();
            loading = false;
            loaded = true;
        } catch (error) {
            console.log(error);
        }
    };
</script>

<div class="wrapper">
    <Game gameData={data.slice(0, 8)} />
    <div class="video-container">
        <video bind:this={videoSource} />

        <div class="buttons">
            <button on:click={videoCamera}>Start Video</button>
            <a class="return-button" href="/">Return</a>
        </div>
    </div>
</div>

<style>
    .wrapper {
        display: flex;
        align-items: center;
        justify-content: space-around;
        gap: 10px;
        background-color: var(--color-offwhite);
    }
    .video-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        height: 100vh;
    }
    video {
        outline: solid;
        width: 800px;
    }
    .buttons{
        display: flex;
        justify-content: space-around;
        align-items: center;
        margin-inline: 8em;
        padding-top: 3em;
    }
    button {
        background-color: #3C6E71;
        color: var(--color-offwhite);
        padding: 0.7em;
        font-size: 18px;
    }
    .return-button {
        background-color: #3C6E71;
        color: var(--color-offwhite);
        font-size: 18px;
        padding: 0.75em;
        border: solid black;
    }


</style>
