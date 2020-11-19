<template>
  <div class="fitur">
    
    <v-container class="my-5" max-width="120px">
      <v-layout row wrap class="mt-8">
        <v-flex xs12 sm6>
          <v-layout row wrap>
            <v-flex xs12 sm6 v-for="features in fitur" :key="features.item">

              <!-- card view item 1  -->
              <v-card flat class="text-sm-center ma-3 rounded-xl">
                <v-responsive class="pt-4 px-4">
                  <v-icon>{{ features.icon }}</v-icon>
                </v-responsive>
                <v-card-text>
                  <div class="subheading">{{ features.item }}</div>
                </v-card-text>
              </v-card>
              <!-- end card view item 1  -->
            
            </v-flex>
          </v-layout>
        </v-flex>
        
            <v-flex xs12 sm6>
              <v-card flat class="rounded-xl ma-3">
                <v-img
                  height="200px"
                  src="https://cdn.pixabay.com/photo/2020/07/12/07/47/bee-5396362_1280.jpg"
                >

                <div class="display-3 text-center mt-12 white--text">
                  12:00
                </div>
                
                <div class="subheading text-center mt-2 white--text">
                  19 November 2020
                </div>
                </v-img>

                <v-card-text>
                  <div class="font-weight-bold ml-8 mb-2">
                    Today
                  </div>

                  <v-timeline
                    align-top
                    dense
                  >
                    <v-timeline-item
                      v-for="message in messages"
                      :key="message.time"
                      :color="message.color"
                      small
                    >
                      <div>
                        <div class="font-weight-normal">
                          <strong>{{ message.from }}</strong> @{{ message.time }}
                        </div>
                        <div>{{ message.message }}</div>
                      </div>
                    </v-timeline-item>
                  </v-timeline>
                </v-card-text>
              </v-card>
            </v-flex>

      </v-layout>
    </v-container>
  
  </div>
</template>

<script>
  export default {
    data: () => ({
      fitur: [
        {
          item: 'Lorem Ipsum 1',
          icon: 'mdi-view-dashboard'
        },
        {
          item: 'Lorem Ipsum 2',
          icon: 'mdi-view-dashboard'
        },
        {
          item: 'Lorem Ipsum 3',
          icon: 'mdi-view-dashboard'
        },
        {
          item: 'Lorem Ipsum 4',
          icon: 'mdi-view-dashboard'
        },
      ],
      messages: [
        {
          from: 'You',
          message: `Sure, I'll see you later.`,
          time: '10:42am',
          color: 'deep-purple lighten-1',
        },
        {
          from: 'John Doe',
          message: 'Yeah, sure. Does 1:00pm work?',
          time: '10:37am',
          color: 'green',
        },
        {
          from: 'You',
          message: 'Did you still want to grab lunch today?',
          time: '9:47am',
          color: 'deep-purple lighten-1',
        },
      ],
    }),
  }
</script>


