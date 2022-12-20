<script setup>
import { JCard, JImage, JBadge } from "@mendmania/ui-name"
import { ref } from "vue";

const test = ref("col");

setTimeout(() => {
  test.value = "row";
}, 3000);

function change() {
  test.value = "col-reverse";
}


const cardOrder = 'col'

const titleStyle = {
  fontSize: "18px",
  fontWeight: "900",
  color: "#36435E",
  textAlign: "left"
}

const showTitle = true 

const formatedInfoBoxStyle = {
  backgroundColor: "#FFFFFF"
}

const showAuthor = true

const showViews = true

const showDate = true

const showThumbnail = true

const showTimeDuration = true

const formatedImageStyle = {
  aspectRatio: "16/9",
  objectFit: "cover",
  objectPosition: "0px 0px;"
}

const formatedBadges = [
  {
    id: "xkaPdQJEo1Z",
    name: "Premium",
    classes: "top-0 left-0",
    style: {
      backgroundColor: "#FFAB00"
    },
    fontStyle: {
      fontSize: "14px",
      fontWeight: "500",
      fontFamily: "Inter",
      fontStyle: "Normal",
      color: "#36435E"
    }
  },
  {
    id: "dy9El7zPg5J",
    name: "New",
    classes: "bottom-0 left-0",
    style: {
      backgroundColor: "#1D79F2"
    },
    fontStyle: {
      fontSize: "14px",
      fontWeight: "500",
      fontFamily: "Inter",
      fontStyle: "Normal",
      color: "#FFFFFF"
    }
  }
]

</script>


<template>
  <div>


    <JCard :order="cardOrder"
         :titleStyle="titleStyle"
         :showTitle="showTitle"
         :detailsStyle="formatedInfoBoxStyle"
         title="Default title"
         :showAuthor="showAuthor"
         author="Author Name"
         :showViews="showViews"
         views="00K Views"
         :showDate="showDate"
         date="00/00/0000"
         :showThumbnail="showThumbnail"
         :showTimeDuration="showTimeDuration"
         timeDuration="03:11">

    <template #image>
      <JImage :imageSrc="'https://ub1doy938d.gjirafa.net/media/zxgzzz/thumbnails/standart.jpg'"
              alt="Video Card Placeholder"
              class="w-full"
              :style="formatedImageStyle" />
    </template>

    <template #badge>
      <template v-for="badge in formatedBadges">
        <JBadge v-if="badge && badge.classes"
                :style="[badge.style, badge.fontStyle]"
                :class="badge.classes">
          {{ badge.name }}
        </JBadge>
      </template>
    </template>

  </JCard>
    
  </div>
</template>