<template> 
<div class="bg-gradient relative !text-white"> 
  <svg width="868" class="w-[50%] right-0 absolute" height="313" viewBox="0 0 868 313" fill="none" xmlns="http://www.w3.org/2000/svg">
  <rect x="2.21777" y="-210.03" width="914.325" height="327.032" rx="22.5" stroke="#E1E1E1" stroke-opacity="0.2" stroke-width="3" stroke-dasharray="10 10"/>
  <rect x="433.303" y="-89.6392" width="914.325" height="327.032" rx="22.5" stroke="#E1E1E1" stroke-opacity="0.2" stroke-width="3" stroke-dasharray="10 10"/>
  <rect x="57.3722" y="-136.49" width="914.325" height="327.032" rx="22.5" stroke="#E1E1E1" stroke-opacity="0.2" stroke-width="3" stroke-dasharray="10 10"/>
  <rect x="488.457" y="-16.1" width="914.325" height="327.032" rx="22.5" stroke="#E1E1E1" stroke-opacity="0.2" stroke-width="3" stroke-dasharray="10 10"/>
  </svg>

  <svg width="329" class="w-[50%] absolute bottom-[-18%] right-[0]" height="616" viewBox="0 0 329 616" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M596.786 612.922C89.6665 638.384 81.5648 204.237 299.729 228.868C513.027 252.95 533.719 535.037 299.729 502.586C9.03679 462.271 -15.7179 104.387 9.03692 52.7558" stroke="#E1B9F3" stroke-width="3"/>
  <path d="M651.257 612.823C97.7151 640.616 88.8717 166.727 327.007 193.613C559.83 219.9 582.417 527.809 327.007 492.387C9.70446 448.382 -17.3163 57.7371 9.7046 1.37932" stroke="#E1B9F3" stroke-width="3"/>
  </svg>

<div class="b-wrapper "> 
  <div class="pt-[20rem] pb-[18rem]"> 
    <div class="flex flex-col md:flex-row gap-[3rem] sm:gap-0"> 
      <div class="w-full pr-[2.2rem]">
        <h1 class="max-w-[106rem] text-white m-auto mb-[2rem]">{{ hero.headline }}</h1>
        <p class="font-jakarta lg max-w-[106rem] m-auto">{{ hero.subHeadline }}</p>
        <div class=" mt-[3.6rem] mb-[5rem] sm:mb-[0]"> 
          <a style="background-color: black !important;" class="b-btn md px-[3rem] accent" :href="hero.btnLink">Get Started</a>
        </div>
      </div>
      <div class="w-full">
        <div class="relative z-[1] b-back">
          <iframe
            class="max-w-[70rem] m-auto w-full aspect-[4/3] rounded-[2rem]"
            :data-src="hero.videoUrl"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            :src="hero.videoUrl"
            vnb-frameid="4576"
          ></iframe>
        </div>
      </div>
    </div>
  </div>
  </div>
</div>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '~/type';
const props = defineProps<{ data?: WizardResponse }>();

const hero = computed(() => {
  const headline = props.data?.agency_wizard.contact.introduction.intro_headline || "Unleash Your Brand Potential With Marketing Done Right";
  const subHeadline = props.data?.agency_wizard.contact.introduction.intro_desc || "Leverage Our Exceptional Services to boost your Online Business growth.";
  const btnLink = props.data?.agency_wizard.contact.introduction.intro_cta_button_link || "#";
  const videoUrl = props.data?.agency_wizard.contact.introduction.intro_video_url || "https://www.youtube.com/embed/s_o9v2EatW8?feature=oembed"
  return { headline, subHeadline, btnLink, videoUrl }
})
</script>

<style scoped> 
.bg-video {
  background: url(/img/video-bg.svg);
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
} 
</style>