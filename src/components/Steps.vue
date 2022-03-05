<template>
  <b-steps v-model="step" :has-navigation="false" class="box pt-4 pb-4">
    <b-step-item
      :label="(step >= 1 && selectedCrossing) || 'Wybierz przejście'"
      icon="crosshairs-gps"
    >
      <div class="is-flex is-flex-wrap-wrap is-justify-content-center pt-4">
        <b-button
          v-for="crossing in crossings"
          :key="crossing"
          type="is-primary"
          size="is-medium"
          @click="selectCrossing"
          class="m-1"
          >{{ crossing }}</b-button
        >
      </div>
    </b-step-item>
    <b-step-item
      :label="step >= 2 ? selectedHelpTypes.join(', ') : 'Potrzeby'"
      icon="help"
    >
      <div class="mt-3">
        <b-checkbox-button
          v-for="helpType in helpTypes"
          :key="helpType"
          v-model="selectedHelpTypes"
          :native-value="helpType.name"
          size="is-medium"
          class="m-1"
        >
          <b-icon :icon="helpType.icon"></b-icon>
          <span>{{ helpType.name }}</span>
        </b-checkbox-button>
      </div>
      <div class="block has-text-centered mt-5">
        <b-button type="is-primary" size="is-medium" @click="nextStep"
          >Dalej</b-button
        >
      </div>
    </b-step-item>
    <b-step-item label="Gdzie szukać pomocy" icon="phone">
      <div class="tile is-ancestor pt-4">
        <div class="tile mt-4 mb-4">
          <div class="card">
            <div class="card-content">
              <div class="media">
                <div class="media-content">
                  <p class="title is-4">John Smith</p>
                  <p class="subtitle is-6">@johnsmith</p>
                </div>
              </div>

              <div class="content">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Phasellus nec iaculis mauris. <a>@bulmaio</a>.
                <a href="#">#css</a>
                <a href="#">#responsive</a>
              </div>
            </div>
          </div>
        </div>
        <div class="tile mt-4 mb-4">
          <div class="card">
            <div class="card-content">
              <div class="media">
                <div class="media-content">
                  <p class="title is-4">John Smith</p>
                  <p class="subtitle is-6">@johnsmith</p>
                </div>
              </div>

              <div class="content">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Phasellus nec iaculis mauris. <a>@bulmaio</a>.
                <a href="#">#css</a>
                <a href="#">#responsive</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </b-step-item>
  </b-steps>
</template>

<script>
export default {
  data() {
    return {
      step: 0,
      crossings: ['Budomierz', 'Hrebenne', 'Korczowa', 'Medyka'],
      selectedCrossing: '',
      helpTypes: [
        { name: 'Mieszkanie', icon: 'home' },
        { name: 'Praca', icon: 'hammer-screwdriver' },
        { name: 'Jedzenie', icon: 'food' },
        { name: 'Leki', icon: 'pill' },
        { name: 'Transport', icon: 'car' },
        { name: 'Zwierzęta', icon: 'paw' },
      ],
      selectedHelpTypes: [],
    };
  },
  methods: {
    selectCrossing(event) {
      this.selectedCrossing = event.target.textContent;
      this.step++;
    },
    nextStep() {
      this.step++;
    },
  },
};
</script>
