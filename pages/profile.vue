<template>
  <v-app>
    <v-container style="max-width: 1200px">
      <div class="display-1 my-4">
        About me
      </div>
      <div class="my-2">
        <div class="title my-2">
          Name : Toshiharu Nakayama
        </div>
        <div class="title my-2">
          BirthYear : 1988
        </div>
        <div class="title my-2">
          Frontend / Backend Developer
        </div>
        <SNS />
      </div>
      <v-divider class="my-3" />
      <SkillGroup
        groupName="Frontend Skills"
        :items="items.filter((item) => item.fields.type === 'Frontend')"
      />
      <v-divider class="my-3" />
      <SkillGroup
        groupName="Backend Skills"
        :items="items.filter((item) => item.fields.type === 'Backend')"
      />
      <v-divider class="my-3" />
      <SkillGroup
        groupName="Other Skills"
        :items="items.filter((item) => item.fields.type === 'Other')"
      />
      <v-btn to="/">
        Back
      </v-btn>
    </v-container>
  </v-app>
</template>

<script>
import SNS from '@/components/atoms/SNS'
import SkillGroup from '@/components/molecules/SkillGroup'
export default {
  components: {
    SkillGroup,
    SNS
  },
  async asyncData({ app }) {
    const entries = await app.$contentful.getEntries()
    console.log(entries.items)
    return {
      items: entries.items.sort((a, b) => b.fields.level - a.fields.level)
    }
  }
}
</script>
