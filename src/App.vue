<template>
  <div class="container">
    <component
      :is="screens[position]"
      @goto="handleGoto"
      @question="handleQuestion"
    />
  </div>
</template>

<script>
  import appInitial from './components/app-initial.vue'
  import appConfirm from './components/app-confirm.vue'
  import appResults from './components/app-results.vue'

  export default {
    components: {
      appInitial,
      appConfirm,
      appResults
    },
    data() {
      return {
        screens: [
          'appInitial',
          'appConfirm',
          'appResults'
        ],
        position: 0,
        question: '',
      }
    },
    methods: {
      handleGoto(position) {
        this.position = position
      },
      handleQuestion(question) {
        this.question = question
      },
    }
  }

</script>

<style>
  @import './assets/style.css';
</style>
