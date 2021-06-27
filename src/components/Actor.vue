<template>
    <div>
        <li id="actor">
            <div class="card mb-3">
                <div class="row g-0">
                    <div class="col-md-4">
                        <img src="https://www.biography.com/.image/ar_1:1%2Cc_fill%2Ccs_srgb%2Cg_face%2Cq_auto:good%2Cw_300/MTE5NDg0MDU1MjIwNjg0MzAz/jack-black-9542484-1-402.jpg" class="img-fluid rounded-start" alt="image">
                    </div>
                    <div class="col-md-8">
                    <div class="card-body">
                        <h5 class="card-title">Card title</h5>
                        <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
                        <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
                    </div>
                    </div>
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
        width: 80%;
        align-content: center;
    }
</style>