<script>

export default {
    props: {
        article: {
            type: Object,
            required: true
        }
    },
}
</script>


<template>
    <div class="article__container">
        <div class="article__image">
            <img :src="article.image" alt="Article image">
        </div>
        <div class="article__content">
            <span class="article__title">
                {{ article.title }}
            </span>
            <p class="article__description">
                {{ article.content }}
            </p>

            <a href="#" class="article__button">ver más</a>
        </div>
    </div>
</template>