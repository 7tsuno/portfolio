<script>
import { Pie } from 'vue-chartjs'

export default {
  extends: Pie,
  props: {
    level: { type: Number, default: 0 }
  },
  mounted() {
    this.renderChart(
      {
        datasets: [
          {
            data: [this.level, 10 - this.level],
            backgroundColor: ['white'],
            borderWidth: 0
          }
        ]
      },
      {
        cutoutPercentage: 90,
        tooltips: { enabled: false }
      }
    )
  }
}
</script>

<style></style>
