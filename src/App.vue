<template>
    <div class="container">
        <app-header :quote-nbr="quotes.length" :max-quotes="maxQuotes"></app-header>
        <app-add-quote @addedQuote="addQuote"></app-add-quote>
        <app-quote-grid :quotes="quotes" @deleteQuote="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: click on a quote to delete it!
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid';
    import AddQuote from "./components/AddQuote";
    import Header from "./components/Header";

    export default {
        data: function () {
            return {
                quotes: ['test'],
                maxQuotes: 8
            }
        },
        methods: {
            addQuote(quote) {
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete quote before adding new one')
                }
                this.quotes.unshift(quote);
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appAddQuote: AddQuote,
            appHeader: Header,
        }
    }
</script>

<style>
</style>
