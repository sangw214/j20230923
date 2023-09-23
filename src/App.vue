<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar
      color="surface-variant"
      title="영업사원 방문관리" />

    <v-main
      class="flex-nowrap align-center justify-center"
      style="min-width: 640px;min-height: 250px;">
      <v-container>
        <v-row
          justify="center"
          class="bg-white my-1"
          no-gutters>
          <v-col cols="7">
            <v-card>
              <v-date-picker
                no-title
                v-model="picker" />
            </v-card>
          </v-col>
          <v-col cols="3">
            <v-sheet class="pa-2 ma-2">
              <v-card>
                오늘
                <v-card height="150">
                  4건
                </v-card>
                완료
                <v-card height="150">
                  15건
                </v-card>   
              </v-card>
            </v-sheet>
          </v-col>
          <v-col cols="10">
            <v-sheet class="pa-2 ma-2">
              방문등록
              <v-card style="overflow-x:auto; white-space: nowrap;">
                <v-data-table
                  v-model="selected"
                  v-model:items-per-page="itemsPerPage"
                  :headers="headers"
                  :items="desserts"
                  item-value="name"
                  show-select
                  class="elevation-1" />              
              </v-card>
            </v-sheet>
            <v-row justify="center">
              <v-col
                cols="auto"
                sm="3">
                <v-btn
                  block
                  rounded="lg"
                  size="large">
                  등록
                </v-btn>
              </v-col>
              <v-col
                cols="auto"
                sm="3">
                <v-btn
                  block
                  rounded="lg"
                  size="large">
                  삭제
                </v-btn>
              </v-col>
            </v-row>
          </v-col>          
        </v-row>
      </v-container>
    </v-main>
    
    <v-footer
      app
      name="footer"
      class="d-flex align-center justify-center"
      style="min-height: 10px;">
      footer Content
    </v-footer>    
  </v-layout>
</template>

<script>
import { VDatePicker } from 'vuetify/labs/VDatePicker'
import { VDataTable } from "vuetify/labs/VDataTable";

export default ({
  components: {
    VDatePicker,
    VDataTable,
  },
  data(){
    return {
      picker: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
      itemsPerPage: 5,
      selected: [],
      headers: [
          {
            title: '시간',
            align: 'start',
            sortable: false,
            key: 'name',
          },
          { title: '방문시간', align: 'end', key: 'calories' },
          { title: '방문자', align: 'end', key: 'fat' },
          { title: '주소', align: 'end', key: 'carbs' },
          { title: '연락처', align: 'end', key: 'protein' },
        ],
        desserts: [
          {
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
          },
          {
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
          },
          {
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
          },
          {
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
          },
          {
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
          },
          {
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
          },
          {
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
          },
          {
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
          },
          {
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
          },
          {
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
          },
        ],      
    }
  }
})
</script>

<style lang="scss">
.v-container {
  padding: 5;
}
div{
  .v-sheet{
    .v-picker-title, 
    .v-date-picker-header, 
    .v-picker__actions {
      display: none;
    }  
  }
}
div{
  .v-data-table-footer__items-per-page,
  .v-data-table-footer__info{
    display: none;
  }

}
</style>