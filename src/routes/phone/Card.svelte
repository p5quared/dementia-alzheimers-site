<script>
    //import { mapActions } from 'vuex';
    import store from "./store/game.js";
    import { createEventDispatcher } from "svelte";
    import back_img from "$lib/game_content/back.png"
    const dispatch = createEventDispatcher();
    export let key;
    export let option = {
        flipped: false,
        name: "",
        img: "",
        show: "img"
    };
    function flip() {
        // action flipcard?
        if (option.flipped) {
            return;
        }
        //option.flipped = !option.flipped;
        //this.flipCard(this.option);
        store.flipCard(option);
        //this.$emit('flipped', this.option);
        dispatch("flipped", option);
    }
    $: flipped = option.flipped ? "flipped" : "";
</script>

<style>
    .container {
        width: 100px;
        height: 121px;
        margin-right: 3px;
        cursor: pointer;
        position: relative;
        perspective: 800px;
    }
    .card {
        width: 100%;
        height: 100%;
        transition: transform 1s;
        transform-style: preserve-3d;
    }
    .card.flipped {
        transform: rotateY(180deg);
    }
    .card img,
    .card p {
        display: block;
        height: 100%;
        width: 100%;
        position: absolute;
        backface-visibility: hidden;
        -webkit-backface-visibility: hidden;
    }
    .card p {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .card .back {
        background: white;
        transform: rotateY(0deg);
    }
    .card .front {
        background: white;
        transform: rotateY(180deg);
    }
    @media screen and (max-width: 450px) {
        .container {
            width: 92px;
            height: 111px;
            margin-right: 1px;
        }
    }
    @media screen and (max-width: 380px) {
        .container {
            width: 85px;
            height: 102px;
            margin-right: 1px;
        }
    }
    @media screen and (max-width: 360px) {
        .container {
            width: 70px;
            height: 84px;
            margin-right: 1px;
        }
    }
</style>

<div class="container" on:click={flip} on:keypress={flip}>
    <div class="card {flipped}">
        {#if option.show == 'image'}
            <img class="front" src={option.img} alt="image of option {option.name}" />
        {/if}
        {#if option.show == 'text'}
            <p class="front">{option.name}</p>
        {/if}
        <img class="back" src={back_img} alt="back-side of a matching card" />
    </div>
</div>