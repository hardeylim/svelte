<script>
    import Card from "./Card.svelte";

    export let feedback = []

    const onDelete = (id) => {
        feedback = feedback.filter(item => item.id !== id)
    }
</script>

{#each feedback as item}
    <Card>
        <div class="num-display">
            {item.rating }
        </div>
        <div on:click={() => onDelete(item.id)} class="close">X</div>
        <div class="tet-display">
            {item.text}
        </div>
    </Card>


<!--    <div class="feedback">-->
<!--        <div class="feedback__header">-->
<!--            <div class="feedback__header__name">{item.id}</div>-->
<!--            <div class="feedback__header__date">{item.rating}</div>-->
<!--        </div>-->
<!--        <div class="feedback__text">{item.text}</div>-->
<!--    </div>-->
{/each}


<style>
    .num-display {
        position: absolute;
        top: -10px;
        left: -10px;
        width: 50px;
        height: 50px;
        background: #ff6a95;
        color: #fff;
        border: 1px #eee solid;
        border-radius: 50%;
        padding: 10px;
        text-align: center;
        font-size: 19px;
    }
    .close {
        position: absolute;
        top: 10px;
        right: 20px;
        cursor: pointer;
        background: none;
        border: none;
    }
</style>
