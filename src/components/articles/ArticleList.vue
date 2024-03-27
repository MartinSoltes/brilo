<template>
    <div v-if="articleFilters">
        <FormattedText v-if="articleFilters.content"
            :class="articleFilters.wrapperClasses"
            :imgSrc=false>
            <div v-html="articleFilters.content" class="formatedText-content"></div>
        </FormattedText>
        <ArticleFilter :filters="articleFilters.filters" :articles="articles"/>
    </div>
    <div v-else class="container">
        <div class="ArticleList">
            <ArticleCard v-for="article in articles" :key="article" :article="article" />
        </div>
    </div>
</template>

<script>
import ArticleCard from '/src/components/articles/ArticleCard.vue';
import ArticleFilter from '/src/components/articles/ArticleFilter.vue';
import FormattedText from '/src/components/FormattedText.vue';

export default {
    components: { ArticleCard, ArticleFilter, FormattedText },
    props: [ 'articles', 'articleFilters' ]
}
</script>

<style>

</style>