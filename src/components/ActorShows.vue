<template>
    <div id="actor-shows">
        <h1>Shows</h1>
        <ul>
        </ul>
    </div>
</template>

<script>
export default {
    name: "ActorShows",
    props: {
        actorID: Number
    }
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