<template>
  <div ref="ganttChart"></div>
</template>

<script>
import { gantt } from 'dhtmlx-gantt'
export default {
  props: {
    tasks: {
      type: Object,
      default () {
        return { data: [], links: [] }
      }
    }
  },

  mounted() {
    gantt.config.date_format = '%Y-%m-%d'
    gantt.init(this.$refs.ganttChart)
    gantt.parse(this.$props.tasks)
  }
}
</script>

<style scoped>
@import "~dhtmlx-gantt/codebase/dhtmlxgantt.css";
</style>
