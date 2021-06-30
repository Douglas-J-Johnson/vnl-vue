<template>
    <div id="selected-actor">
        <h1>{{ selectedActor.name }}</h1>
        <img id="selected-actor-image" :src="selectedActor.image.original" alt="image"/>
    </div>
</template>

<script>
export default {
    name: "SelectedActor",
    props: {
        selectedActor: Object
    }
}
</script>

<style scoped>
    h1 {
        margin: 1rem;
    }

    #selected-actor {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    #selected-actor-image {
        width: 50%;
        margin: 1rem;
    }
</style>