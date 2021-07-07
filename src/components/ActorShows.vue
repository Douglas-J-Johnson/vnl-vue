<template>
    <div id="actor-shows">
        <h1>Shows</h1>
        <ul>
            <Show></Show>
        </ul>
    </div>
</template>

<script>
import Show from "./Show"

export default {
    name: "ActorShows",
    props: {
        actorID: Number
    },
    components: {
        Show
    },
    computed: {},
    methods: {}
}
</script>

<style scoped>
    #actor-shows {
        padding: 0;
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    ul {
        margin: 0;
        padding: 0;
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: stretch;
        list-style-type: none;

    }
</style>