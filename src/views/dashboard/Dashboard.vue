<template>
  <v-container>
    <h1 class="text-h3 mb-2">Dashboard Page</h1>

    <v-sheet class="mb-4" color=surface-variant rounded>
      <v-breadcrumbs :items="breadcrumbs"></v-breadcrumbs>
    </v-sheet>

    <v-row>
      <v-col cols="12">
        <v-card title="Dashboard cards" prepend-icon="mdi-numeric">
          <v-data-iterator :items="cards" items-per-page="6" :page="page">
            <template #default="{ items }">
              <v-container>
                <v-row>
                  <v-col cols="4" v-for="(item, n) in items" :key="n">
                    <v-skeleton-loader type="card" :loading="loading">
                      <v-card
                        :title="`Card title ${item.raw}`"
                        border
                        flat
                        subtitle="Card subtitle"
                        text="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
                      >
                        <template #actions>
                          <v-spacer></v-spacer>

                          <v-btn text="More details" border></v-btn>
                        </template>
                      </v-card>
                    </v-skeleton-loader>
                  </v-col>
                </v-row>
              </v-container>
            </template>

            <template #footer="{ pageCount }">
              <v-pagination
                v-model="page"
                :length="pageCount"
                class="my-4"
                size="x-small"
              ></v-pagination>
            </template>
          </v-data-iterator>
        </v-card>
      </v-col>

      <v-col cols="12">
        <v-card title="Latest User Events" prepend-icon="mdi-calendar">
          <v-infinite-scroll :height="300" :items="events" :onLoad="load">
            <template v-for="(item, index) in events" :key="item">
              <div :class="['pa-2', index % 2 === 0 ? 'bg-grey-lighten-2' : '']">
                User Event #{{ item }}
              </div>
            </template>
          </v-infinite-scroll>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
  import { onMounted } from 'vue';
  import { ref } from 'vue'

  const breadcrumbs = ref([
    {
      title: 'Home',
      to: '/'
    },
    {
      title: 'Dashboard',
      active: true
    }
  ])
  const page = ref(2)
  const events = ref([])
  const cards = ref(Array.from({ length: 18 }, (k, v) => v + 1))
  const loading = ref(true)

  async function api () {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve(Array.from({ length: 10 }, (k, v) => v + (events.value.at(-1) ? events.value.at(-1) + 1 : 1)))
      }, 1000)
    })
  }

  async function load ({ done }) {
    // Perform API call
    const res = await api()

    events.value.push(...res)

    done('ok')
  }

  onMounted(() => {
    setTimeout(() => {
      loading.value = false
    }, 1500)
  })
</script>
