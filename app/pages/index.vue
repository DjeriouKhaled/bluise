<template>
  <section class="home">
    <div class="py-24 md:py-36 mx-auto flex flex-wrap flex-col md:flex-row items-center">
      <div class="flex flex-col w-full xl:w-3/5 justify-center lg:items-start overflow-y-hidden">
        <div v-html="$md.render(welcomeText)" class="home__welcome markdown" />

         <div class="contact-me" style="background-color: #f9f9f9; border: 1px solid #ddd; padding: 20px; border-radius: 5px; width: 300px; margin: 0 auto;">
        <h2>Contact Me</h2>
        <ul>
            <li><strong>Email:</strong> <a href="mailto:khaledjr2018@gmail.com">khaledjr2018@gmail.com</a></li>
            <li><strong>Telegram:</strong> <a href="https://t.me/jirou_fujimi">https://t.me/jirou_fujimi</a></li>
        </ul>
    </div>
        
        
      <div class="flex flex-col w-full xl:w-2/5">
        <img
          alt="Hero"
          class="rounded shadow-xl"
          src="/images/uploads/io.png"
        />
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component({
  // Called to know which transition to apply
  transition() {
    return 'slide-left';
  },
})
export default class Home extends Vue {
  welcomeText = settings.welcomeText;

  get posts(): Post[] {
    return this.$store.state.posts;
  }
}

</script>
