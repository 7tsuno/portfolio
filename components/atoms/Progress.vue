<script>
import { Pie } from 'vue-chartjs'
import Chart from 'chart.js'

export default {
  extends: Pie,
  props: {
    level: { type: Number, default: 0 }
  },
  mounted() {
    const level = this.level
    this.addPlugin({
      afterDraw(chart, go) {
        const ctx = chart.ctx

        // 中央にテキスト表示
        const fontSize = 15
        const fontStyle = 'normal'
        const fontFamily = 'Helvetica Neue'
        ctx.fillStyle = '#FFF'
        ctx.font = Chart.helpers.fontString(fontSize, fontStyle, fontFamily)

        ctx.textAlign = 'center'
        ctx.textBaseline = 'middle'

        ctx.fillText(level, chart.width / 2, chart.height / 2 + 5)
      }
    })
    this.renderChart(
      {
        datasets: [
          {
            data: [level, 10 - level],
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
