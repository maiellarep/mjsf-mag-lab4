<template>
  <div>
    <page-header/>
    <p> Modal dialog with activator</p>
    <b-modal close-btn size="xs" title="My title" @click:outside="showModal = false">
      <template slot="title" slot-scope="scope">{{scope.title}} {{scope.visible}}</template>
      <template #footer="scope">
        <button class="btn btn-primary" @click="scope.close">Close</button>
      </template>
      Modal with activator
      <template #activator="{on}">
        <button class="btn btn-primary" @click="on">Open</button>
      </template>
    </b-modal>
    <hr>
    <p> Modal dialog with model</p>
    <b-modal v-model="showModal" close-btn size="xs" title="My title" @click:outside="showModal = false">
      Modal with model
    </b-modal>

    <button type="button" class="btn btn-primary" @click="showModal = !showModal">
      Launch demo modal
    </button>
  </div>
</template>

<script>
  import BModal from "../../components/bootstrap/BModal";
  import PageHeader from "./PageHeader";

  export default {
    name: "Home",
    components: {PageHeader, BModal},
    data() {
      return {
        showModal: false
      }
    }
  }
</script>

