<template>
  <v-carousel
      cycle
      height="100vh"
      hide-delimiter-background
      show-arrows-on-hover
  >
    <template v-slot:prev="{ on, attrs }">
      <v-btn
          color="white"
          v-bind="attrs"
          v-on="on"
          icon
      >
        <v-icon>mdi-arrow-left</v-icon>
      </v-btn>
    </template>
    <template v-slot:next="{ on, attrs }">
      <v-btn
          color="white"
          v-bind="attrs"
          v-on="on"
          icon
      >
        <v-icon>mdi-arrow-right</v-icon>
      </v-btn>
    </template>
    <v-carousel-item>
      <v-sheet
          height="100%"
      >
        <v-row
            class="fill-height"
            align="center"
            justify="center"
        >
          <div class="text-h6">

            <v-row>
              <v-col cols="12" lg="6">
               <div class="pa-16">
                 <p>
                   Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
                 </p>
               </div>
              </v-col>
              <v-col cols="12" lg="6">
                <div class="slide-img" style="border: 1px solid black">
                  <div class="mask">
                      <div class="cover-img-mask">
                        <v-img contain height="600" :src="require('@/assets/sham1.png')"></v-img>
                      </div>
                  </div>
                  <v-img contain height="500" :src="require('@/assets/sham1.png')"></v-img>
                </div>

              </v-col>

            </v-row>
          </div>
        </v-row>
      </v-sheet>
    </v-carousel-item>

  </v-carousel>
</template>

<script>
export default {
  name: "Carousel",
  data () {
    return {

    }
  },
}
</script>

<style scoped>
p {
  text-align: justify;
  text-justify: inter-word;
}

.slide-img
{
  animation: mymove .5s;
  position: relative;
}
@keyframes mymove {
  from{
    margin-top: 300px;
    transform: scale(4) rotate(20deg);
  }
  to{
    margin-top: 0px;
    transform: scale(1) rotate(0deg);
  }
}

@keyframes resizemask {
  from{
   height: 100%;


  }
  to{
    height: 0%;
  }

}
.mask{
  display: block;
  position: absolute;
  width: 100%;
  z-index: 2;
  height: 0%;
  animation: resizemask 1.5s;
  overflow: hidden;
}

.cover-img-mask{
  border: 1px solid black;
  margin: auto;
}




</style>