<template>
    <nuxt-link :to="localePath(to)" :class="classObject">
        <slot></slot>
    </nuxt-link>
</template>

<script>
export default {
    name: 'CoreLocaleLink',
    props: {
        to: {
            type: String,
            default: '',
        },
        customized: {
            type: Boolean,
            default: false,
        },
        highlight: {
            type: Boolean,
            default: false,
        },
        underline: {
            type: Boolean,
            default: false,
        },
    },
    computed: {
        classObject() {
            return {
                'core-localeLink': true,
                highlight: this.highlight,
                underline: this.underline,
                '--customized': this.customized,
            }
        },
    },
}
</script>

<style lang="postcss" scoped>
/* TODO: Update highlight variant style with the design */
.highlight {
    color: #c2a53a;
}
.highlight:hover {
    color: #9387ff;
}

.underline {
    @apply underline;
}

.core-localeLink:not(.highlight):not(.--customized) {
    color: #c2a53a;
}

.core-localeLink:not(.highlight):not(.--customized):hover {
    color: #9387ff;
}
</style>
