<template>
  <div :class="{'modal': true, 'is-active': true}">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title">Exporting STL</p>
        <button class="delete" aria-label="close" @click="close"></button>
      </header>
      <section class="modal-card-body">
          <div class="columns">
            <div class="column content">
                <p class="is-size-4">
                  <progress class="progress is-small is-primary" max="100" v-if="seconds !== 0"></progress>
                  <progress class="progress is-small is-primary" max="100" v-if="seconds === 0" value="100"></progress>
                </p>
                <p>
                  <br/>Thank You for using qrcode2stl.
                </p>
            </div>
          </div>
      </section>
      <footer class="modal-card-foot">
        <button class="button" @click="close">OK</button>
      </footer>
    </div>
  </div>
</template>

<script>
import { bus } from '../main';

export default {
  name: 'ExportModal',
  components: {
  },
  data() {
    return {
      seconds: 0,
      exportAd: '',
      showingThankYou: false,
    };
  },
  mounted() {
  },
  methods: {
    close() {
      bus.$emit('closeExportModal');
    },
    showThanks() {
      this.showingThankYou = true;
    },
  },
};
</script>
