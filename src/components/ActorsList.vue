<template>
    <div class="actors-list">
        <ul>
            <Actor v-for="actor in actors" :key="actor.id" :actor="actor"></Actor>
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
    }
}
</script>

<style scoped>
    #actors-list {
        width: 80%;
    }

    ul {
        padding: 0px;
    }
</style>
