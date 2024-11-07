<template>
    <div class="result">
        <div class="title">
            {{ results[resultsIndex].title }}
        </div>
        <div class="desc">
            {{ results[resultsIndex].desc }}
        </div>
    </div>
</template>

<script>
export default {
    props: ["results", "totalCorrect"],
    computed: {
        resultsIndex() {
            let index = 0;
            this.results.forEach((el, i) => {
                if (el.min <= this.totalCorrect && el.max >= this.totalCorrect) {
                    index = i;
                }
            });
            return index;
        }
    }
}
</script>