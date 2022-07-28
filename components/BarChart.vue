
<script>
import { Bar } from 'vue-chartjs'
import _ from 'lodash'

export default {
    extends: Bar,
    props: {
        chartData: {
            type: Object,
            default: null
        },
        options: {
            
            type: Object,
            default: null,
        },
    },
    watch: {
            chartData: {
               handler () {
                const clone = _.cloneDeep(this.chartData)
                this.renderChart(clone, this.options)
               },
               deep: true
            }
        },
    mounted() {
        this.renderChart(this.chartData, this.options)
    }
}
</script>
