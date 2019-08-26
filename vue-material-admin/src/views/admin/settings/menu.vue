<template>
  <div class="list-table">
    <v-container grid-list-xl fluid>
      <v-layout row wrap>
        <v-flex sm12>
          <h3>Fuess Menu</h3>
        </v-flex>
       
        <v-flex lg8>
          <v-card>
            <v-card-actions class="pb-2">
              
              <v-btn color="primary" @click="save()">Add</v-btn>
              <v-btn color="primary" @click="save()">Save</v-btn>
              
            </v-card-actions>

          <v-data-table dense :headers="basic.headers" :items="basic.items" hide-actions hide-default-header hide-default-footer class="elevation-1" >
            <template slot="items" slot-scope="props">
              <td>{{ props.item.order }}</td>
              <td>{{ props.item.id }}</td>
              <td>{{ props.item.title }}</td>
              <td>{{ props.item.parameter }}</td>
              <td>
                    <v-btn depressed outline icon fab dark color="primary" small>
                      <v-icon>edit</v-icon>
                    </v-btn>
                    <v-btn depressed outline icon fab dark color="pink" small>
                      <v-icon>delete</v-icon>
                    </v-btn>
              </td>
              
             
            </template>
          </v-data-table>
            </v-card>
        </v-flex>
        
      </v-layout>
    </v-container>
  </div>
</template>

<script>
//import { Items as Users } from "@/api/user"
import topMenu from "@/api/FuessMenuSetting"
export default {
  data() {
    return {
      search: "",
      basic: {
       
        headers: [
          {
            text: "order",
            value: "order"
          }
          ,
          {
            text: "id",
            value: "id"
          },
          {
            text: "title",
            value: "title"
          },
          {
            text: "parameter",
            value: "parameter"
          },
          {
            text: "active",
            value: "active"
          }
          
        ],
        items: topMenu
      }
    }
  }
}
</script>
