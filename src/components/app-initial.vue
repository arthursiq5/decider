<template>
    <div>
        <h1>Ask a question</h1>
        <div class="mb-3">
            <input
                type="text"
                name="question"
                class="form-control"
                id="question"
                v-model="question"
            />
        </div>
        <button
            v-if="question"
            class="btn"
            @click="handleNext"
        >
            Next
        </button>

        <div v-if="error" class="error">
            Question is too short
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            question: '',
            error: false,
        }
    },
    methods: {
        handleNext(e) {
            e.preventDefault()

            if (this.question.length <= 5) {
                this.error = true
            } else {
                this.error = false
                this.$emit('goto', 1)
                this.$emit('question', this.question)
            }
        }
    },
}

</script>

<style>

</style>
