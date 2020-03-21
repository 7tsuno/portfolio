<template>
  <v-app>
    <div class="containerMe my-4">
      <div class="display-1 my-4">
        About me
      </div>
      <div class="my-2">
        <div class="headline my-2">
          Name : Toshiharu Nakayama
        </div>
        <div class="headline my-2">
          BirthYear : 1988
        </div>
        <div class="headline my-2">
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
    </div>
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

<style>
.containerMe {
  width: 90%;
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;
  padding: 0px 2em;
}
</style>
