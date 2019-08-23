<template>
  <div id="page-text-fields">
    <v-container grid-list-xl fluid>
      <v-layout row wrap>
        <v-flex sm12>
          <v-card>
            <v-toolbar card prominent color="primary" dark>
              <v-toolbar-title class="body-2">System Setup</v-toolbar-title>
              <v-spacer></v-spacer>
            </v-toolbar>
            <v-card-text>
              <v-layout row>
                <v-flex xs4>
                  <v-subheader>System Title</v-subheader>
                </v-flex>
                <v-flex xs8>
                  <v-text-field name="input-1" label="Name" color="primary" id="testing"></v-text-field>
                </v-flex>
              </v-layout>

              <v-layout row>
                <v-flex xs4>
                  <v-subheader>Upload Logo</v-subheader>
                </v-flex>
                <v-flex xs8>
                  <upload-btn ref="button" title="Browse" @file-update="update"></upload-btn>
                  <div v-if="isShow" class="error--text">You can only upload images</div>
                </v-flex>
              </v-layout>
            </v-card-text>
            <v-card-actions class="pb-2">
              <v-spacer></v-spacer>
              <v-btn color="primary" @click="save()">Save</v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import UploadButton from "vuetify-upload-button"
export default {
  components: {
    "upload-btn": UploadButton
  },
  data() {
    return {
      email: "",
      rules: {
        required: value => !!value || "Required."
      },
      isShow: false
    }
  },
  computed: {},
  methods: {
    update(file) {
      const type = file.type.split("/")
      if (type[0] != "image") {
        this.isShow = true
      } else {
        this.isShow = false
      }
      console.log(file.type)
    },
    save() {}
  }
}
</script>
