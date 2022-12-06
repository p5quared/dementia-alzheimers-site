<script>
    import chessboard from "$lib/images/chessboard.png";
    let videoSource = null;
    let loading = false;
    let loaded = false;
    const videoCamara = async () => {
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
    <img id="chess" src={chessboard} alt="placeholder for games; chess">
    <div class="video-container">
        <!-- svelte-ignore a11y-media-has-caption -->
        <video bind:this={videoSource}></video>

        <div class="buttons">
            <button on:click={videoCamara}>Start Video</button>
            <a class="return-button" href="/">Return</a>
        </div>
    </div>
</div>

<style>
    .wrapper {
        display: flex;
        align-items: center;
        gap: 10px;
        background-color: var(--color-offwhite);
    }
    .video-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        height: 100vh;
    }
    #chess {
        height: 100vh;
    }
    video {
        outline: solid;
        width: 625px;
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
