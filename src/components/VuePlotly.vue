<template>
  <div>
    <div ref="plotlyId" name="plotly"></div>
  </div>
</template>

<script>
export default {
  name: "VuePlotly",
  inheritAttrs: false,
  props: {
    data: {
      type: Array,
      required: true,
    },
    layout: {
      type: Object,
      required: true,
    },
    config: {
      type: Object,
      required: false,
      default: () => ({ responsive: true }),
    },
  },
  data() {
    return {
      ready: false,
    };
  },
  watch: {
    data: {
      handler() {
        this.setGraph();
      },
      deep: true,
    },
    layout: {
      handler() {
        this.setGraph();
      },
      deep: true,
    },
    config: {
      handler() {
        this.setGraph();
      },
      deep: true,
    },
  },
  mounted() {
    this.ready = true;
    this.setGraph();
  },
  methods: {
    async setGraph() {
      if (
        !this.ready ||
        !this.$refs.plotlyId ||
        !this.data ||
        !this.layout ||
        typeof window === "undefined"
      )
        return;
      const Plotly = await import("plotly.js-dist-min");
      Plotly.newPlot(this.$refs.plotlyId, this.data, this.layout, this.config);
    },
  },
};
</script>
