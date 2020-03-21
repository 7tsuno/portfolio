<template>
  <v-app>
    <v-content>
      <v-container class="fill-height" fluid>
        <v-row>
          <v-col cols="12" align="center" justify="center">
            <div class="display-4 font-weight-thin">
              Toshiahru Nakayama
            </div>
            <div class="display-1 font-weight-thin">
              I'm Frontend/Backend Developer
            </div>
          </v-col>
          <v-col align="center" justify="center">
            <v-btn to="profile" class="mb-3">
              About me
            </v-btn>
            <SNS />
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import SNS from '@/components/atoms/SNS'
export default {
  components: {
    SNS
  }
}
</script>

<style></style>
