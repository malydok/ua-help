<template>
  <div class="container">
    <section class="section">
      <h1 class="title">Znajdź pomoc</h1>
      <h2 class="subtitle mb-6">
        Sprecyzuj poniżej na jakim przejściu granicznym jesteś i jakie są twoje
        konkretne potrzeby.
      </h2>
      <Steps />
    </section>
  </div>
</template>

<script>
import Steps from './components/Steps.vue';

export default {
  name: 'App',
  components: {
    Steps,
  },
};
</script>
