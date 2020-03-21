<template>
  <v-card>
    <v-card-title class="headline">{{ item.fields.name }}</v-card-title>
    <v-card-text>Level : {{ item.fields.level }}</v-card-text>
    <div class="pa-6 mt-n7">
      <Progress :level="item.fields.level" />
    </div>
  </v-card>
</template>

<script>
import Progress from '@/components/atoms/Progress'
export default {
  components: {
    Progress
  },
  props: {
    item: { type: Object, default: null }
  }
}
</script>

<style></style>
