<template>
  <div>
    <h5>
      {{ $tr('durationLabel') }}
    </h5>
    <KRadioButton
      v-for="duration in durationOptions"
      :key="duration.value"
      v-model="selectedDuration"
      :value="duration.value"
      :label="duration.label"
    />
  </div>
</template>

<script>

import { metadataTranslationMixin } from 'shared/mixins';
import { DurationDropdownMap, CompletionDropdownMap } from 'shared/constants';

const DEFAULT_SHORT_ACTIVITY = 600;
const DEFAULT_LONG_ACTIVITY = 3000;

export default {
  name: 'EditCompletionModal',
  mixins: [metadataTranslationMixin],
  props: {
    required:{
      type: Boolean,
      default: false,
    },
    resourceDuration: {
      type: Number,
      default: null,
    },
  },
  data() {
    return {
      selectedDuration: '',
    }
  },
  computed: {
    durationOptions() {
      const options = Object.values(DurationDropdownMap).map((value) => ({
        value,
        label: this.translateMetadataString(value),
      }));
      options.push({
        value: CompletionDropdownMap.reference,
        label: this.translateMetadataString(CompletionDropdownMap.reference),
      });
      return options;
    }
  },
  methods: {
    
  },
  watch: {
    selectedDuration(value) {
      console.log("value", value)
    },
  },
  $trs: {
    durationLabel: 'Duration',
  }
}

</script>

<style scoped>
</style>