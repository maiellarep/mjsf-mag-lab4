<template>
  <div>
    <page-header/>
    <p> Modal dialog with activator</p>
    <b-modal close-btn size="xs" title="My title" @click:outside="showModal = false">
      <template slot="title" slot-scope="scope">{{scope.title}} {{scope.visible}}</template>
      <template #footer="scope">
        <button class="btn btn-primary" @click="scope.close">Dismiss</button>
      </template>
      Modal with activator
      <template #activator="{on}">
        <button class="btn btn-primary" @click="on">Open Modal</button>
      </template>
    </b-modal>

    <br>

    <b-alert close-btn show="dismissCountDown" v-bind:duration=1 title="Alert!">
      <template slot="title" slot-scope="scope">{{scope.title}} {{scope.visible}}</template>
      <template #footer="scope">
        <button class="btn btn-primary" @click="scope.close">Dismiss</button>
      </template>
      Alert with activator
      <template #activator="{on}">
        <button class="btn btn-primary" @click="on">Open Alert</button>
      </template>
    </b-alert>
    <hr>
    <p> Modal dialog with model</p>
    <b-modal v-model="showModal" close-btn size="xs" title="My title" @click:outside="showModal = false">
      Modal with model
    </b-modal>
    <br>
    <button type="button" class="btn btn-primary" @click="showModal = !showModal">
      Launch demo modal
    </button>

    <b-alert  show="dismissCountDown" v-bind:duration=3 v-model="showAlert" lose-btn size="xs" title="Alert!">
      Alert with model
    </b-alert>

    <button type="button" class="btn btn-primary" @click="showAlert = !showAlert">
      Launch demo Alert
    </button>
  </div>
</template>

<script>
  import BModal from "../../components/bootstrap/BModal";
  import BAlert from "../../components/bootstrap/BAlert";
  import PageHeader from "./PageHeader";
  export default {
    name: "Home",
    components: {PageHeader, BModal, BAlert},
    data() {
      return {
        showModal: false,
        showAlert: false
      }
    },
  }
</script>

