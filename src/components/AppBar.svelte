<script>
    import TopAppBar from "@smui/top-app-bar"
    import JQ_ from "jquery"



</script>

<style lang="scss">
    @media screen and (max-width: 576px){
        #siteName {
            font-size: 0.6em;
        }
    }
    @mixin posCenter() {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    :global(.myHeader) {
        @include posCenter();
        height: 100px;

        font-size: 50px;

        font-family: "Roboto Light";
        overflow: hidden;

        .cool-div {
            position: absolute;
            width: 100%;
            height: 100px;
            overflow: hidden;
            background-color: wheat;
            @include posCenter();

            video {
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 100px;
                object-fit: cover;
            }

            h2 {
                position: absolute;
                @include posCenter();
                margin: 0;
                top: 0;
                left: 0;
                width: 100%;
                height: 100px;
                background: white;
                color: black;
                font-size: 0.8em;
                text-transform: uppercase;
                word-spacing: 10px;
                mix-blend-mode: screen;



            }
        }
    }

</style>

<TopAppBar class="myHeader" variant="static" color="secondary">
    <div class="cool-div">
        <video id="video" autoplay loop>
            <source src="./gradient.mp4">
        </video>
        <h2 id="siteName">My Github Repos</h2>


    </div>
</TopAppBar>
