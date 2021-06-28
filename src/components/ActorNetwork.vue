<template>
    <div id="actor-network">
        Actor Network
        <div id="actor-description">
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
        </div>
    </div>
</template>

<script>
import SelectedActor from './SelectedActor'

export default {
    name: "ActorNetwork",
    components: {
        SelectedActor
    },
    props: {
        selectedActor: Object
    },
    methods: {
        resetSearch() {
            console.log("reset search")
            this.$emit('resetSearch');
        }
    }
}
</script>

<style scoped>

</style>