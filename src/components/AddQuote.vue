<template>
    <div class="row">
        <form action="">
            <div class="class-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Add new quote</label>
                <textarea class="form-control" rows="3" v-model="quote"></textarea>
            </div>
            <div class="class-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createQuote">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        return: function () {
            return {
                quote: ''
            };
        },
        methods: {
            createQuote() {
                if (this.quote.trim() !== ''){
                    this.$emit('addedQuote', this.quote);
                    this.quote = '';
                }
            }
        }
    }
</script>
