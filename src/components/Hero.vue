<script>
    export default {
        props: {
            image: {
                type: String,
                required: true
            },

            title: {
                type: String,
                required: true
            }
        },
        data() {

        },
        watch: {
            
        },
        mounted() {
            
        },
        methods: {
           
        }
    }
</script>


<template>
    <div class="hero">
        <div class="hero__background">
            <img src="../assets/img/hero_BG.png" class="hero__image" alt="Hero background">
        </div>

        <div class="hero__title-container">
            <h1 class="hero__title">
                El secreto de tu cocina
            </h1>
        </div>

        <div class="hero__separator">
        </div>
    </div>
</template>