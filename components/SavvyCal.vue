<template>
  <div id="booking-page">
  </div>
</template>

<script>
export default {
  mounted() {
    this.initializeSavvyCal()
    this.inlineSavvyCal()
  },
  methods: {
    initializeSavvyCal() {
      window.SavvyCal = window.SavvyCal || function () {
        (SavvyCal.q = SavvyCal.q || []).push(arguments)
      };
      try {
        SavvyCal('init');
      } catch (e) {
        console.error(e)
      }
    },
    inlineSavvyCal() {
      try {
        SavvyCal('inline', {
          link: 'w3security/public',
          selector: '#booking-page',
          theme: 'dark',
          metadata: {
            source: 'https://w3security.github.io/meet'
          }
        });
      } catch (e) {
        console.error(e)
      }
    }
  }
}
</script>

<style scoped></style>
