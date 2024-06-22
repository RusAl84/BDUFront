<template>
  <q-page>
    <div class="box">
      <q-card class="big-card">
        <div class="q-pa-md row items-start q-gutter-md">
          <q-card class="my-card" style="min-width: 900px">
            <div class="flexrow">
              <div>
                <q-card-section>
                  <div class="text-h6">
                    Загрузите файл отчета ПО ScanOVAL сертифицированного ФСТЭК
                    России (в формате HTML):
                  </div>
                </q-card-section>

                <q-card-section>
                  <q-uploader
                    :url="hostae_uploadimg"
                    label="Загрузите файл отчета ПО ScanOVAL .html/*"
                    square
                    flat
                    bordered
                    single
                    @uploaded="fileUploaded"
                    accept=".html, Web/*"
                    style="min-width: 600px; max-width: 600px"
                  />
                </q-card-section>
              </div>
            </div>
          </q-card>
        </div>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";
import axios from "axios";

export default {
  data() {
    return {
      file: "",
      hostae_uploadimg: "http://localhost:5000/upload_data",
      input_text: ref(""),
    };
  },
  methods: {
    handleFileUpload() {
      this.file = this.$refs.file.files[0];
    },
    fileUploaded({ files, xhr }) {
      // console.log(xhr.response);
    },
  },
};
</script>
<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 250px
.big-card
  flex-direction: column
  justify-content: center
  align-items: center
  width: 90%
  height: 90%
.box
  display: flex
  flex-flow: row nowrap
  justify-content: center
  align-content: center
  align-items: center
  margin: 3%
</style>
