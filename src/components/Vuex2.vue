<template>
  <h1 v-if="status === 'success'">Success {{ complex.deep }}</h1>
  <h1 v-else-if="status === 'error'">Error</h1>
  <h1 v-else>Loading</h1>
</template>

<script>
import { mapState } from 'vuex';

export default {
  name: 'vuex2',
  data() {
    return {
      complex: null,
    };
  },
  computed: mapState(['status']),
  watch: {
    status(newValue, oldValue) {
      console.log(`Updating from ${oldValue} to ${newValue}`);

      // Do whatever makes sense now
      if (newValue === 'success') {
        this.complex = {
          deep: 'some deep object',
        };
      }
    },
  },
};
</script>
