<template>
    <div id="actor-network">
        <section id="actor-description" class="odd-section">
            <SelectedActor
                :selectedActor="selectedActor"
            ></SelectedActor>
            <div class="d-grid gap-2 col-6 mx-auto">
                <button
                    class="btn btn-primary"
                    type="button"
                    @click="resetSearch">
                    Search Again
                </button>
            </div>
        </section>
        <section id="actor-shows" class="even-section">
            <ActorShows
                :actorID="selectedActor.id"
            ></ActorShows>

        </section>
    </div>
</template>

<script>
import SelectedActor from './SelectedActor'
import ActorShows from './ActorShows'

export default {
    name: "ActorNetwork",
    components: {
        SelectedActor,
        ActorShows
    },
    props: {
        selectedActor: Object
    },
    methods: {
        resetSearch() { this.$emit('resetSearch'); }
    }
}
</script>

<style scoped>
    #actor-description {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .odd-section {
        margin: 1rem;
        background-color: #fff;
    }

    .even-section {
        margin: 1rem;
        background-color: #eee;
    }
</style>