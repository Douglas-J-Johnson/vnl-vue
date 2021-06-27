<template>
    <div class="actors-list">
        <ul>
            <Actor v-for="actor in actors"
                :key="actor.id"
                :actor="actor"
                @selectActor="selectActor"
            ></Actor>
        </ul>
    </div>
</template>

<script>
import Actor from './Actor.vue'

export default {
    name: "ActorsList",
    props: {
        actors: Array
    },
    components: {
        Actor
    },
    methods: {
        selectActor(actorID) {
            this.$emit('selectActor', actorID);
        }
    }
}
</script>

<style scoped>
    #actors-list {
        padding: 0;
        width: 100%;
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
