<script>
    import {onMount} from "svelte"
    import Card, {Content,Actions} from "@smui/card"
    import Button from "@smui/button"

    let resArr = []
    onMount(async () => {
        const getRepos = await fetch("https://api.github.com/users/ahmeteneskcc/repos")
                .then(res => res.json()).then(res => resArr = [...resArr,...res])

        console.log(resArr)
    })


</script>

<style lang="scss">

    :global(.cards) {
        font-family: "Roboto Light";
        width: 20vw;
        width: 30%;
        min-width: 300px;
        margin-bottom: 30px;
        font-family: "Roboto Thin";
        font-size: 20px;
        h3 {
            font-size: 30px;
            text-align: center;
            opacity: 70%;
        } p {
        @extend h3;
        font-size: 15px;
                  }

    }
    .card_container {
        flex-direction: row;
        flex-wrap: wrap;
        display: flex;
        width: 100%;
        height: 80vh;
        justify-content: space-around;
        align-items: center;
    }


</style>
<div class="card_container">
    {#each resArr as repos}
        <Card class="cards"><Content><h3>{repos.name}</h3><p>{repos.description}</p></Content><Actions fullBleed>
            <Button on:click={() => window.location.href=repos.html_url} color="secondary" >Go To Github<i class="material-icons">arrow_forward</i></Button>
            {#if repos.homepage != null}
                <Button on:click={() => repos.homepage = null ? window.location.href=repos.homepage : console.log("Page Could not Found")} color="secondary" >Go To Web Page<i class="material-icons">arrow_forward</i></Button>
                {/if}


        </Actions></Card>
    {/each}
</div>

