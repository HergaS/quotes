<template>
    <div class="container">
        <appHeader :quoteCount="allQuotes.length" :maxQuotes="maxQuotes" />
        <appQuoteInput @quoteAdded="newQuote" />
        <appQuotesGrid :allQuotes="allQuotes" @quoteDeleted="deleteQuote" />
        <div class="row marg-top">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it</div>
            </div>
        </div>
    </div>
</template>

<script>
    import Header from './components/Header.vue'
    import QuoteInput from './components/QuoteInput.vue'
    import QuotesGrid from './components/QuotesGrid.vue'

    export default {
        components: {
            appHeader: Header,
            appQuoteInput: QuoteInput,
            appQuotesGrid: QuotesGrid
        },
        data() {
            return {
                maxQuotes: 10,
                allQuotes: []
            }
        },
        methods: {
            newQuote(quote) {
                if (this.allQuotes.length >= this.maxQuotes) {
                    return alert('Please delete Quotes first!');
                }
                this.allQuotes.push(quote);
            },
            deleteQuote(index) {
                this.allQuotes.splice(index, 1);
            }
        }
    }
</script>

<style>
.marg-top {
    margin-top: 5vh;
}
</style>
