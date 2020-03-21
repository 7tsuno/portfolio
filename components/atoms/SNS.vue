<template>
  <div>
    <v-tooltip bottom>
      <template v-slot:activator="{ on }">
        <v-btn
          icon
          large
          href="https://github.com/7tsuno"
          target="_blank"
          v-on="on"
        >
          <v-icon large>mdi-github</v-icon>
        </v-btn>
      </template>
      <span>Github</span>
    </v-tooltip>
    <v-tooltip bottom>
      <template v-slot:activator="{ on }">
        <v-btn
          icon
          large
          href="https://twitter.com/7tsunoD"
          target="_blank"
          v-on="on"
        >
          <v-icon large>mdi-twitter</v-icon>
        </v-btn>
      </template>
      <span>Twitter</span>
    </v-tooltip>
    <v-tooltip bottom>
      <template v-slot:activator="{ on }">
        <v-btn
          icon
          large
          href="https://qiita.com/7tsuno"
          target="_blank"
          v-on="on"
        >
          <v-icon large>mdi-note</v-icon>
        </v-btn>
      </template>
      <span>Qiita</span>
    </v-tooltip>
  </div>
</template>

<script></script>

<style></style>
