<template>
    <a :href="link"
        class="button"
        :class="{
            'button--secondary':  (variant == 'secondary'),
            'button--primary': (variant != 'secondary'),
            'active': buttonActive
        }"
        @click.prevent="toggleActiveClass"
        >
        <slot></slot>
    </a>
</template>

<script>
export default {
    props: ['link', 'variant', 'active'],
    methods: {
        toggleActiveClass () {
            this.buttonActive = !this.buttonActive
        }
    },
    data() {
        return {
            buttonActive: this.active ? this.active : false,
        }
    }

}
</script>

<style>

</style>