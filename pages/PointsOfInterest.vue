<template>
  <div class="points-of-interest">
    <div class="section-title">
      <h2>Points of Interest</h2>
    </div>
    <PointOfIntCard v-for="(card, index) in cards" :key="index" :card="card" />
  </div>
</template>

<script>
import PointOfIntCard from '../components/PointOfIntCard.vue'

export default {
  components: {
    PointOfIntCard,
  },
  data() {
    return {
      cards: [
        {
          title: 'Great Sept of Baelor',
          text:
            'The Great Sept of Baelor was the center of the Faith of the Seven, the dominant religion in seven of the nine constituent regions of the realm, and the seat and residence of the High Septon, the topmost official within the Faith.',
          image: 'great-sept-exterior-close.jpg',
        },
        {
          title: 'Flea Bottom',
          text:
            'Flea Bottom is the largest slum district in the city. Davos Seaworth and Armeca hail from Flea Bottom.',
          image: 'flea-bottom.jpg',
        },
        {
          title: "Littlefinger's Brothel",
          text:
            "Littlefinger's brothel is a high-end establishment whose prostitutes cater to richest classes in the city. It has since been attacked and destroyed by the newly reinstated Faith Militant under leadership from the High Sparrow.",
          image: 'littlefingers-brothel.webp',
        },
        {
          title: 'The Iron Throne',
          text:
            "The Iron Throne was the throne upon which the King of the Andals, the Rhoynar, and the First Men sat, located in the Great Hall of the Red Keep in the city of King's Landing. Besides the monarchs themselves, only their Hand could sit on the Iron Throne. The Iron Throne was also a metonym, along with 'the crown,' referring to the monarchy that rules the Seven Kingdoms and the authority of the monarchy (e.g. 'rebellion against the Iron Throne').",
          image: 'great-hall.webp',
        },
      ],
    }
  },
}
</script>

<style>
.points-of-interest {
  width: 100%;
  height: fit-content;
  padding: 2vw;
  background: var(--main-brown);
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  gap: 2vw;
  justify-content: flex-start;
  align-items: center;
}
.section-title {
  width: 40vw;
  height: 12.5vw;
  display: flex;
  justify-content: center;
  align-items: center;
  color: var(--main-white);
}
@media screen and (min-width: 700px) {
  .points-of-interest {
    height: 75vw;
  }
}
</style>
