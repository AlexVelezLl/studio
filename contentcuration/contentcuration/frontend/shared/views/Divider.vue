<template>
  <hr
    :style="dividerStyle"
  />
</template>

<script>
  export default {
    name: 'Divider',
    props: {
      margin: {
        type: String,
        default: '24px',
      },
    },
    computed: {
      dividerStyle() {
        return {
          border: 0,
          borderBottom: `1px solid ${this.$themeTokens.fineLine}`,
          margin: '1em 0',
        };
      },
    },
  }
</script>
