<template>
    <v-app id="app">
    <div>
      <h3> 書いた絵 </h3>
      <v-row>
          <div v-for="(image, index) in lists" :key="index">
            <v-col>
            <v-img :src="image.url"
              max-height="250"
              max-width="250"
              @click="setDialogUrl(index)"
              >
            </v-img>
          </v-col>
          </div>
      </v-row>
      <v-dialog v-model="dialog" width="1000" contained>
        <v-img :src="dialogUrl" :max-height="800" :max-width="1000" 
        contain ></v-img>
      </v-dialog>
    </div>
  </v-app>
</template>

<script>
  export default {
    // components: { vGallery },
    data() {
      return {
        lists: [
          {title: '桃華', url:'/mysite//momoka.jpeg'},
          {title: '千冬', url:'/mysite/chifuyu.jpeg'}
        ],
        dialog: false,
        dialogUrl: '',
      }
    },
    computed: {
    },
    methods: {
      setDialogUrl(index) {
        this.dialogUrl = this.lists[index].url
        this.dialog = true
      },
    }
  }
</script>