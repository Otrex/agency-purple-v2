<template> 
<div class="relative z-2"> 
  <div class="py-[10rem] b-wrapper"> 
    <div class="w-full flex-col sm:flex-row  mx-auto flex gap-[3rem]">
      <div class="sm:max-w-[40rem] w-full relative z-1">
        <div class="w-[70rem] aspect-square bg-[#3B57F41A] z-[-1] bottom-[40%] right-[35%] absolute rounded-full"></div>
        <div class="sm:max-w-[40rem] w-full max-h-[70rem] h-full rounded-[4rem] overflow-hidden">
          <img :src="image" class="w-full h-full object-cover" />
        </div>
      </div>

      <div style="--bg-r: calc(4rem + 1px)" class="flex w-full mt-[5rem] flex-col sm:pl-[2.3rem] w-full gap-[2rem]">
        <div style="--bg-r: calc(4rem + 1px)" class="p-[5rem] border-gradient rounded-[4rem]"> 
          <h2 class="leading-[7.2rem] text-black mb-[2rem] break-words">Get Free Consultation</h2>
          <p class="font-jakarta tracking-tight pl-[.5rem] mb-[5rem]">Fill out your details Below to get a free Consultation.</p>
          <div class="w-full">
            <div v-html="consult" class="b-force"></div>
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
const consult = computed(() => {
  return props.data?.agency_wizard.leads_collector || `
    <div class="mb-[2rem]"> 
      <input class="b-input" placeholder="Full Name" />
    </div>
    <div class="mb-[4rem]"> 
      <input class="b-input" placeholder="Email Address" />
    </div>
    <div> 
      <a class="b-btn md text-[--accent-100]">Get Started</a>
    </div>
  `
})

const image = computed(() => {
  return props.data?.agency_wizard.leads_image || '/img/leads.png';
})
</script>

<style> 
    
</style>