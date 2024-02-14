<template>
  <v-container>
    <v-row justify="center" no-gutters>
      <v-col sm="4" md="8" class="mt-16">
        <v-app-bar :elevation="0">
          <template v-slot:prepend>
            <v-app-bar-nav-icon></v-app-bar-nav-icon>
          </template>

          <v-app-bar-title>Application Bar</v-app-bar-title>

          <template v-slot:append>
            <v-btn icon="mdi-heart"></v-btn>

            <v-btn icon="mdi-magnify"></v-btn>

            <v-btn icon="mdi-dots-vertical"></v-btn>
          </template>
        </v-app-bar>

        <v-autocomplete
          label="Autocomplete"
          :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"
        ></v-autocomplete>

        <v-card>
          <v-container fluid>
            <v-row>
              <v-col cols="12">
                <v-autocomplete
                  v-model="values"
                  :items="items"
                  label="Default"
                ></v-autocomplete>
              </v-col>

              <v-col cols="12">
                <v-autocomplete
                  v-model="values"
                  :items="items"
                  density="comfortable"
                  label="Comfortable"
                ></v-autocomplete>
              </v-col>

              <v-col cols="12">
                <v-autocomplete
                  v-model="values"
                  :items="items"
                  density="compact"
                  label="Compact"
                ></v-autocomplete>
              </v-col>
            </v-row>
          </v-container>
        </v-card>

        <div>
          <v-container fluid>
            <v-row>
              <v-col cols="12" sm="4" md="4">
                <v-checkbox
                  v-model="ex4"
                  label="red"
                  color="red"
                  value="red"
                  hide-details
                ></v-checkbox>
                <v-checkbox
                  v-model="ex4"
                  label="red-darken-3"
                  color="red-darken-3"
                  value="red-darken-3"
                  hide-details
                ></v-checkbox>
              </v-col>
              <v-col cols="12" sm="4" md="4">
                <v-checkbox
                  v-model="ex4"
                  label="indigo"
                  color="indigo"
                  value="indigo"
                  hide-details
                ></v-checkbox>
                <v-checkbox
                  v-model="ex4"
                  label="indigo-darken-3"
                  color="indigo-darken-3"
                  value="indigo-darken-3"
                  hide-details
                ></v-checkbox>
              </v-col>
              <v-col cols="12" sm="4" md="4">
                <v-checkbox
                  v-model="ex4"
                  label="orange"
                  color="orange"
                  value="orange"
                  hide-details
                ></v-checkbox>
                <v-checkbox
                  v-model="ex4"
                  label="orange-darken-3"
                  color="orange-darken-3"
                  value="orange-darken-3"
                  hide-details
                ></v-checkbox>
              </v-col>
            </v-row>

            <v-row class="mt-12">
              <v-col cols="12" sm="4" md="4">
                <v-checkbox
                  v-model="ex4"
                  label="primary"
                  color="primary"
                  value="primary"
                  hide-details
                ></v-checkbox>
                <v-checkbox
                  v-model="ex4"
                  label="secondary"
                  color="secondary"
                  value="secondary"
                  hide-details
                ></v-checkbox>
              </v-col>
              <v-col cols="12" sm="4" md="4">
                <v-checkbox
                  v-model="ex4"
                  label="success"
                  color="success"
                  value="success"
                  hide-details
                ></v-checkbox>
                <v-checkbox
                  v-model="ex4"
                  label="info"
                  color="info"
                  value="info"
                  hide-details
                ></v-checkbox>
              </v-col>
              <v-col cols="12" sm="4" md="4">
                <v-checkbox
                  v-model="ex4"
                  label="warning"
                  color="warning"
                  value="warning"
                  hide-details
                ></v-checkbox>
                <v-checkbox
                  v-model="ex4"
                  label="error"
                  color="error"
                  value="error"
                  hide-details
                ></v-checkbox>
              </v-col>
            </v-row>
          </v-container>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
const ex4 = ['red', 'indigo', 'orange', 'primary', 'secondary', 'success', 'info', 'warning', 'error', 'red darken-3', 'indigo darken-3', 'orange darken-3']
</script>
