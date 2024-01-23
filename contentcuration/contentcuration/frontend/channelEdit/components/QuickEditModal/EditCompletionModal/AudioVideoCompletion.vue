<template>
  <div>
    <Divider/>
    <DurationInput
      required
    />
  </div>
</template>

<script>

  import DurationInput from './inputs/DurationInput';
  import Divider from 'shared/views/Divider';

  export default {
    name: 'EditCompletionModal',
    props: {
      nodeId: {
        type: String,
        required: true,
      },
    },
    components: {
      DurationInput,
    },
    data() {
      return {
      }
    },
    methods: {
      
    },
  }

</script>

<style scoped>
</style>