<template>
  <v-card>
    <v-card-title class="title">{{ item.fields.name }}</v-card-title>
    <div class="pa-10 mt-n7">
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
