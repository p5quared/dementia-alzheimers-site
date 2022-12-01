<script>
    let videoSource = null;
    let loading = false;
    const videoCamara = async () => {
        try {
            loading = true;
            videoSource.srcObject = await navigator.mediaDevices.getUserMedia({
                video: true,
            });
            videoSource.play();
            loading = false;
        } catch (error) {
            console.log(error);
        }
    };
</script>

<div class="wrapper">
    <h1>abctitle</h1>
    <video bind:this={videoSource}>
        {#if loading}
            <h1>LOADING</h1>
        {/if}
    </video>
    <button on:click={videoCamara}>Play</button>
</div>

<style>
    .wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    video {
        height: 400px;
        width: 100%;
        outline: solid;
    }
    h1 {
        font-size: 54px;
    }
</style>