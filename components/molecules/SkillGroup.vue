<template>
  <div>
    <div class="display-1">
      {{ groupName }}
    </div>
    <v-row>
      <v-col
        cols="12"
        sm="6"
        md="4"
        lg="3"
        v-for="item in items"
        :key="item.sys.id"
      >
        <Skill :item="item" />
      </v-col>
    </v-row>
  </div>
</template>

<script>
import Skill from '@/components/atoms/Skill'

export default {
  components: {
    Skill
  },
  props: {
    groupName: { type: String, default: '' },
    items: { type: Array, default: () => [] }
  }
}
</script>

<style></style>
