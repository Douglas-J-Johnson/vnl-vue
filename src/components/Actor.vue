<template>
    <div id="actor">
        <li>
            <div class="card">
            <img :src="actor.person.image.medium" class="card-img-top" alt="image">
                <div class="card-body">
                    <h5 class="card-title">{{ actor.person.name }}</h5>
                </div>
            </div>
        </li>
    </div>
</template>

<script>
export default {
    name: "Actor",
    props: {
        actor: Object
    }
}
</script>

<style scoped>
    #actor {
        width: 10rem;
        margin: 1rem;
        padding: 0;
    }

    li {
        width: 100%;
    }

    h5 {
        text-align: center;
    }
</style>