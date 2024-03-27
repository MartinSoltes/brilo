<template>
  <div class="ArticleCard" :data-category="article.category">
    <div>
        <img v-if="article.img" :src="article.img" :alt="article.title" class="img-fluid mb-3">
        <div>
            <h4 class="text-center mb-3">{{ article.title }}</h4>
            <p class="text-center">{{ article.annotation }}</p>
        </div>
    </div>
    <div class="ArticleCard-cta">
        <Button v-if="article.curl"
                :link="article.curl"
            >{{"Zjistit více"}}</Button>
    </div>
  </div>
</template>

<script>

import Button from '/src/components/Button.vue'
export default {
    props: ['article'],
    components: { Button }
}
</script>

<style>

</style>