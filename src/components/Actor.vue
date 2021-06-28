<template>
    <div id="actor">
        <li @click="selectActor">
            <div class="card">
            <img :src="actorImageURL" class="card-img-top" alt="image">
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
    },
    computed: {
        actorImageURL() {
            let imageURL = 'https://prepsec.org/wp-content/uploads/2017/09/unknown-person-icon-Image-from.png';

            if (this.actor.person.image?.medium) {
                imageURL = this.actor.person.image.medium;
            }

            return imageURL;
        }
    },
    methods: {
        selectActor() {
            this.$emit('selectActor', this.actor.person);
        }
    }
}
</script>

<style scoped>
    #actor {
        width: 10rem;
        margin: 1rem;
        padding: 0;
    }

    .card {
        height: 100%;
        opacity: 0.5;
    }

    .card:hover {
        opacity: 1;
    }

    .card-img-top {
        height: 80%;
    }

    li {
        width: 100%;
        height: 100%;
    }

    h5 {
        text-align: center;
    }
</style>