<template>
    <div class="container">
        <div v-if="filters" class="button-group justify-content-center pb-4 mb-2">
            <div v-for="(filter, index) in filters" :key="index">
                <input type="radio"
                    :id="filter.value+index"
                    class="btn-check"
                    v-model="activeFilter"
                    :value="filter.value">
                <label class="button button--secondary"
                    :for="filter.value+index"
                    :class="{'active': activeFilter == filter.value}"
                >{{ filter.label }}</label>
            </div>
        </div>
        <div class="ArticleList">
            <ArticleCard v-for="article in filteredArticles" :key="article" :article="article"/>
        </div>
    </div>
</template>

<script>
import ArticleCard from '/src/components/articles/ArticleCard.vue'

export default {
    props: [ 'filters', 'articles' ],
    components: { ArticleCard },
    data() {
        return {
            activeFilter: '',
        }
    },
    computed: {
        filteredArticles() {
            if (this.activeFilter == '') return this.articles
            else return this.articles.filter((article) => (article.category == this.activeFilter))
        },
    }
}
</script>

<style>

</style>