# Vue Plotly

A thin wrapper of Plotly.js for Vue 3. This package provides a Vue component that makes it easy to use Plotly.js in your Vue 3 applications.

## Installation

```bash
npm install vue-plotly
```
## Usage

In your Vue component:
```bash
<template>
	<VuePlotly :data="data" :layout="layout" :config="config" />
</template>

<script>
import VuePlotly from 'vue-plotly';

export default {
	components: {
		VuePlotly
	},
	data() {
		return {
			data: [...],  // your data here
			layout: {...},  // your layout here
			config: {...},  // your config here
		};
	},
};
</script>
```
# Props
```bash
data: (Array) The data for the plot. Required.
layout: (Object) The layout of the plot. Required.
config: (Object) The configuration options for the plot. Optional.
```
## License
MIT

Please replace the placeholders in the usage example with actual data, layout, and config examples.