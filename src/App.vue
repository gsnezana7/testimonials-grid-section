<script setup>
import Footer from './components/AppFooter.vue';
import AppCard from './components/AppCard.vue';

const testimonials = [
  {
    id: 1,
    avatar: "../public/images/image-daniel.jpg",
    name: "Daniel Clifford",
    status: "Verified Graduate",
    title: "I received a job offer mid-course, and the subjects I learned were current, if not more so, in the company I joined.I honestly feel I got every penny’s worth.",
    quote: ` "I was an EMT for many years before I joined the bootcamp. I’ve been looking to make a
  transition and have heard some people who had an amazing experience here.I signed up
  for the free intro course and found it incredibly fun! I enrolled shortly thereafter.
  The next 12 weeks was the best - and most grueling - time of my life.Since completing
  the course, I’ve successfully switched careers, working as a Software Engineer at a VR startup."`,
    color: 'hsl(180, 62%, 55%)',
    gridArea: 'Daniel'
  },
  {
    id: 2,
    avatar: "../public/images/image-jonathan.jpg",
    name: "Jonathan Walters",
    status: "Verified Graduate",
    title: "The team was very supportive and kept me motivated",
    quote: ` “ I started as a total newbie with virtually no coding skills. I now work as a mobile engineer
  for a big company. This was one of the best investments I’ve made in myself. ”`,
    color: 'hsl(180, 62%, 55%)',
    gridArea: 'Jonathan'
  },
  {
    id: 3,
    avatar: "../public/images/image-jeanette.jpg",
    name: "Jeanette Harmon",
    status: "Verified Graduate",
    title: "An overall wonderful and rewarding experience",
    quote: `“ Thank you for the wonderful experience! I now have a job I really enjoy, and make a good living
  while doing something I love. ”`,
    color: 'hsl(180, 62%, 55%)',
    gridArea: 'Jeanette'
  },
  {
    id: 4,
    avatar: "../public/images/image-patrick.jpg",
    name: "Patrick Abrams",
    status: "Verified Graduate",
    title: `"Awesome teaching support from TAs who did the bootcamp themselves. Getting guidance from them and
  learning from their experiences was easy."`,
    quote: ` “ The staff seem genuinely concerned about my progress which I find really refreshing. The program
  gave me the confidence necessary to be able to go out in the world and present myself as a capable
  junior developer. The standard is above the rest. You will get the personal attention you need from
  an incredible community of smart and amazing people. ”`,
    color: 'hsl(180, 62%, 55%)',
    gridArea: 'Patrick '
  },
  {
    id: 5,
    avatar: "../public/images/image-kira.jpg",
    name: "Kira Whittle",
    status: "  Verified Graduate",
    title: `" Such a life-changing experience. Highly recommended!`,
    quote: `“ Before joining the bootcamp, I’ve never written a line of code. I needed some structure from
  professionals who can help me learn programming step by step. I was encouraged to enroll by a former
  student of theirs who can only say wonderful things about the program. The entire curriculum and staff
  did not disappoint. They were very hands-on and I never had to wait long for assistance. The agile team
  project, in particular, was outstanding. It took my learning to the next level in a way that no tutorial
  could ever have. In fact, I’ve often referred to it during interviews as an example of my developent
  experience. It certainly helped me land a job as a full-stack developer after receiving multiple offers.
  100% recommend! ”`,
    color: 'hsl(180, 62%, 55%)',
    gridArea: 'Kira'
  },
];

</script>

<template>
  <section class="container">
    <ul class="features-grid">
      <li v-for="card in testimonials" :key="card.id"
        :class="['features-grid__item', `features-grid__item--${card.gridArea}`]">
        <AppCard :avatar="card.avatar" :name="card.name" :status="card.status" :title="card.title"
          :backgroundColor="card.backgroundColor" />
      </li>
    </ul>
  </section>

  <Footer />
</template>

<style lang="scss" scoped>
@use "./assets/styles/abstracts" as *;

.container {
  margin: 0 auto;
  padding: rem(30);
  padding-top: fluid(56, 103, 375, 768);
  width: 100%;
  max-width: rem(1440);
}

.features-grid {
  display: grid;
  gap: rem(32);
  padding: 0;
  list-style: none;
  grid-template-columns: 1fr;

  @media (width >=rem(1024)) {
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);
    align-items: center;
    grid-template-areas: "supervisor builder calc"
      "supervisor karma   calc";

    &__item {
      &--supervisor {
        grid-area: supervisor;
      }

      &--builder {
        grid-area: builder;
      }

      &--karma {
        grid-area: karma;
      }

      &--calc {
        grid-area: calc;
      }
    }
  }
}
</style>
