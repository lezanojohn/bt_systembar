<template>
  <v-app id="inspire">
    <v-system-bar app>
      <v-spacer></v-spacer>

      <v-icon>mdi-square</v-icon>

      <v-icon>mdi-circle</v-icon>

      <v-icon>mdi-triangle</v-icon>
    </v-system-bar>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Blog de telecontrol</v-toolbar-title>
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      fixed
      temporary
    >
      <!--  -->
    </v-navigation-drawer>

    <v-main class="grey lighten-2">
      <v-container>
        <v-row>
          <template v-for="category in categories">
            <v-col
              :key="category.id"
              class="mt-2"
              cols="12"
            >
              <strong>{{ category.name }}</strong>
            </v-col>

            <v-col
              v-for="j in 6"
              :key="`${category.id}${j}`"
              cols="6"
              md="2"
            >
              <v-sheet height="150"></v-sheet>
            </v-col>
          </template>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: null,
      categories: [
        { id: 0, name: 'Agua Potable' },
        { id: 1, name: 'Agua Servida' },
        { id: 2, name: 'Distribución' },
        { id: 3, name: 'Recolección' },
        { id: 4, name: 'Mesa Soporte' },
        { id: 8, name: 'Fiscalizaciones' },
        { id: 6, name: 'Analítica' },
        { id: 5, name: 'Informes' },
        { id: 7, name: 'Extracción de datos' },
      ]
    }),
  }
</script>