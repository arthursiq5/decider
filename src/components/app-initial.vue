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
            {{ question }}
        </div>
        <button class="btn">
            Next
        </button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            question: ''
        }
    }
}

</script>

<style>

</style>
