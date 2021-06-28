<template>
    <div id="selected-actor">
        Selected Actor
        {{ selectedActor.id }}
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
</style>