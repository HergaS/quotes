<template>
    <div class="row marg-top">
        <Quote v-for="(quote, index) in allQuotes" :key="index" @click.native="deleteQuote(index)">
            {{ quote }}
        </Quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'
    
    export default {
        props: ['allQuotes'],
        components: {
            Quote
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>

<style scoped>

</style>