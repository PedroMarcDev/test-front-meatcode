<script>

import axios from 'axios'
import Article from './Article.vue'

export default {
        data() {
            return {
                articles: [],
                isActiveFilter: "todos",
                filters: ['todos', "productos", "recetas", "consejos"],
                isDisabledButton: false,
                isLoading: false,
            }
        },
        watch: {
            
        },
        mounted() {
            this.fetchingFilter()
        },
        methods: {

            fetchingFilter() {
                axios.get('https://5eed24da4cbc340016330f0d.mockapi.io', {
                    // params: {
                    //     filter: this.isActiveFilter === "todos" ? "" : this.isActiveFilter,
                    // },
                })

                .then(response => {
                    console.log("response", response.data);
                    this.articles = response.data;
                    console.log("fetch", this.articles);
                })
                .catch(error => {
                    console.log(error);
                })
                .finally(() => {
                    this.isLoading = false
                })
            
            },
        }
    }
</script>


<template>
    <div class="articles__filter">
        <button v-for="filter in filters" :key="filter" class="articles__filter-option" :class="{'articles__filter-option--selected': isActiveFilter === filter,
        }" @click="() => handleFilter(filter)">
            {{ filter }}

            <img src="../assets/img/arrow.svg" alt="Arrow icon">
        </button>
    </div>

    <div class="articles__list">
        <div class="article__container">
            <div class="article__image">
                <img src="../assets/img/hero_BG.png" alt="Article image">
            </div>
            <div class="article__content">
                <span class="article__title">
                    Curabitur vulputate placerat tristique nam libero eros
                </span>
                <p class="article__description">
                    Malesuada tortor, facilisi vel turpis ullamcorper. Mattis egestas mattis nulla pretium. Arcu pretium, tempor,
                </p>

                <a href="#" class="article__button">ver más</a>
            </div>
        </div>
        <div class="article__container">
            <div class="article__image">
                <img src="../assets/img/hero_BG.png" alt="Article image">
            </div>
            <div class="article__content">
                <span class="article__title">
                    Curabitur vulputate placerat tristique nam libero eros
                </span>
                <p class="article__description">
                    Malesuada tortor, facilisi vel turpis ullamcorper. Mattis egestas mattis nulla pretium. Arcu pretium, tempor,
                </p>

                <a href="#" class="article__button">ver más</a>
            </div>
        </div>
        <div class="article__container">
            <div class="article__image">
                <img src="../assets/img/hero_BG.png" alt="Article image">
            </div>
            <div class="article__content">
                <span class="article__title">
                    Curabitur vulputate placerat tristique nam libero eros
                </span>
                <p class="article__description">
                    Malesuada tortor, facilisi vel turpis ullamcorper. Mattis egestas mattis nulla pretium. Arcu pretium, tempor,
                </p>

                <a href="#" class="article__button">ver más</a>
            </div>
        </div>
        <div class="article__container">
            <div class="article__image">
                <img src="../assets/img/hero_BG.png" alt="Article image">
            </div>
            <div class="article__content">
                <span class="article__title">
                    Curabitur vulputate placerat tristique nam libero eros
                </span>
                <p class="article__description">
                    Malesuada tortor, facilisi vel turpis ullamcorper. Mattis egestas mattis nulla pretium. Arcu pretium, tempor,
                </p>

                <a href="#" class="article__button">ver más</a>
            </div>
        </div>
        <div class="article__container">
            <div class="article__image">
                <img src="../assets/img/hero_BG.png" alt="Article image">
            </div>
            <div class="article__content">
                <span class="article__title">
                    Curabitur vulputate placerat tristique nam libero eros
                </span>
                <p class="article__description">
                    Malesuada tortor, facilisi vel turpis ullamcorper. Mattis egestas mattis nulla pretium. Arcu pretium, tempor,
                </p>

                <a href="#" class="article__button">ver más</a>
            </div>
        </div>
        <!-- <Article v-for="article in articles.slice(0, 9)" :article="article" /> -->
    </div>
</template>