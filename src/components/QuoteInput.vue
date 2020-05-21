<template>
    <div class="row marg-top">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Quotes</label>
                <textarea v-model="quote" class="form-control" rows="5"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 text-center form-group">
                <button class="btn btn-primary" @click.prevent="addQuote">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                quote: ''
            }
        },
        methods: {
            addQuote() {
                if (this.quote === '') {
                    return alert('Please write a Quote first!');
                }
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }   
    }
</script>

<style scoped>
label {
    font-size: 1.8rem;
}

</style>