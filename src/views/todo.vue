<template>
  <v-container>
    <ass dum="Register" />
    <v-container>
      <v-row>
        <v-col cols="12" sm="6" md="3">
          <v-text-field v-model="name" label="ชื่อ" solo></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <v-text-field v-model="lastname" label="นามสกุล" solo></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <v-text-field
            v-model="idstu"
            label="รหัสนักศึกษา"
            solo
          ></v-text-field>
        </v-col>
      </v-row>
      <v-select
        v-model="subject"
        :items="items"
        label="คณะ"
        dense
        solo
      ></v-select>
    </v-container>

    <v-btn @click="addTodo()" color="warning" dark> summit </v-btn>
    <v-container>
      <v-list dense>
        <v-list-item-group v-model="selectedItem" color="primary">
          <v-list-item v-for="(item, i) in additems" :key="i">
            <v-list-item-content>
              <v-list-item-title v-text="item.text"></v-list-item-title>
            </v-list-item-content>
            <v-btn
              class="mx-2"
              fab
              dark
              small
              color="error"
              @click="deleteTodo(i)"
            >
              <v-icon dark> mdi-minus </v-icon>
            </v-btn>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-container>
  </v-container>
</template>

<script>
import ass from "../components/ass.vue";
export default {
  data() {
    return {
      subject: "",
      name: "",
      lastname: "",
      cs: "",
      cs2: "",
      idstu: "",
      items: ["วิทยาศาสตร์ ", "เกษตรกรรม", "แพทย์", "รังศีเทคนิค"],
      selectedItem: 1,
      additems: [],
    };
  },
  components: {
    ass,
  },

  methods: {
    addTodo() {
      //console.log(this.subject + this.work);
      this.additems.push({
        text:
          "คณะ: " +
          this.subject +
          " " +
          this.name +
          " " +
          this.lastname +
          " " +
          this.idstu +
          " " +
          this.cs +
          " " +
          this.cs2,
      });
    },
    deleteTodo(index) {
      this.additems.splice(index, 1);
    },
  },
};
</script>

<style></style>
