<script>
    import store from "./store/game";
    import Dashboard from "./Dashboard.svelte";
    import Chessboard from "./Chessboard.svelte";
    import PlayStatus from "./PlayStatus.svelte";
    import { STATUS } from "./store/status_enums";
    import { shuffle } from "$lib/game_content/shuffle.js";
    export let gameData = [];
    let show = "text";
    let settings = {
        show: "image",
        gameSize: gameData.length
    };
    function restartGame() {
        return {
            leftMatched: settings.gameSize,
            highestSpeed: localStorage.getItem("highestSpeed") || "",
            status: STATUS.READY,
            cards: shuffle(gameData.slice(0, settings.gameSize)).map(item => {
                item.flipped = false;
                item.show = settings.show;
                return item;
            }),
            elapsedMs: 0,
            displayEnd: false,
            displayNameInput: false,
            displaySettings: false,
            ranks: [],
            userName: localStorage.getItem("userName") || ""
        };
    }
    function triggerRestart() {
        store.reset(restartGame());
    }
    function settingsClose(event) {
        settings = event.detail;
        triggerRestart();
    }
    triggerRestart();
</script>

<style>
    #game-panel {
        position: relative;
        width: 450px;
        height: 670px;
        border: 4px solid #bdbdbd;
        border-radius: 2px;
        background-color: #faf8ef;
        padding: 10px;
        display: flex;
        flex-direction: column;
    }
    @media screen and (max-width: 450px) {
        #game-panel {
            width: 100%;
            height: 100%;
            justify-content: space-around;
        }
    }
</style>

<div id="game-panel">
    <Dashboard
            leftMatched={$store.leftMatched}
            highestSpeed={$store.highestSpeed}
            on:restart={triggerRestart} />
    <Chessboard cards={$store.cards} />
    <PlayStatus
            status={$store.status}
            elapsedMs={$store.elapsedMs}
            gameSettings={settings}
            on:settingsClose={settingsClose} />
</div>