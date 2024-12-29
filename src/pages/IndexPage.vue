<template>
  <q-page class="flex flex-center text-white justify-center items-center">

    <div class="row">
      <q-input placeholder="Counter" color="warning" filled input-class="text-center text-white text-h6"
        v-model="data.name" />

    </div>

    <div class="row full-width ">
      <div class="col text-center">
        <q-btn v-touch-repeat:300:300:300:300:50.mouse="decreaseCounter" outline round color="warning" size="lg"
          icon="remove" @click="decreaseCounter()" />
      </div>
      <div class="col text-center text-h2">{{ data.counter }}</div>
      <div class="col text-center">
        <q-btn v-touch-repeat:300:300:300:300:50.mouse="increaseCounter" outline round color="warning" size="lg"
          icon="add" @click="increaseCounter" />
      </div>
    </div>

    <div class="row full-width">
      <div class="col text-center">
        <q-btn round color="warning" icon="restart_alt" size="xl" padding="md" @click="resetCounter">
          <q-tooltip>
            Reset Counter
          </q-tooltip>
        </q-btn>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { reactive } from 'vue'

const data = reactive({
  counter: 0,
  name: "",
});

const increaseCounter = () => {
  data.counter++;
}

const decreaseCounter = () => {
  if (data.counter > 0)
    data.counter--;
}

const resetCounter = () => {
  data.counter = 0;
}

</script>

<style lang="scss">
.q-page {
  max-width: 700px;
  margin: 0 auto;
}
</style>
