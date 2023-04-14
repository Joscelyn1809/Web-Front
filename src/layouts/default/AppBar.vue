<template>
  <v-app-bar :elevation="4" dark prominent
    image="https://images.saymedia-content.com/.image/t_share/MTkzODU1MjgzMjUxMTkzMzI4/svg-wave-generator.gif"
    density="compact" shrink-on-scroll src="https://picsum.photos/1920/1080?random" fade-image-on-scroll
    scroll-target="scrolling-techniques-4">

    <template v-slot:img="{ props }">
      <v-img v-bind="props" gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"></v-img>
    </template>

    <v-toolbar-title>
      Buenos Dias
    </v-toolbar-title>
    <v-spacer></v-spacer>

    <v-btn icon="mdi-dots-vertical"></v-btn>
  </v-app-bar>

  <v-sheet id="scrolling-techniques-3" class="overflow-y-auto" max-height="600">
  </v-sheet>

</template>

<script>
export default {
}
</script>
