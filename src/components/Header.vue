<template>
    <div class="row">
        <div class="col-sm-12">
            <h3 class="marg-top">Quotes Added</h3>
            <div class="progress">
                <div class="progress-bar" :class="{ hide: quoteCount == 0 }" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
                    {{ quoteCount }} / {{ maxQuotes }}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quoteCount', 'maxQuotes']
    }
</script>

<style scoped>
h3 {
    font-weight: bold;
}
.hide {
    visibility: hidden;
}
</style>