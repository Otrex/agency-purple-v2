<template> 
  <nav class="w-full relative text-white">
    <div ref="nav" class="fixed w-full z-[100] inset-0 bottom-auto py-[1.6rem]">
      <div class="flex b-wrapper justify-between">
        <div class="flex items-center">
          <div class="max-w-[18rem] max-h-[5rem]"> 
            <img :src="logo" class="w-full h-full object-cover" />
          </div>
        </div>
        <div class="sm:flex hidden items-center">
          <ul class="flex gap-[2.4rem] items-center"> 
            <li><a href="#" class="b-nav-item">Home</a></li>
            <li><a href="#services" class="b-nav-item">Our Services</a></li>
            <li><a href="#about" class="b-nav-item">About Us</a></li>
            <li><a href="#testimonials" class="b-nav-item">Testimonial</a></li>
          </ul>
        </div>
        <div class="flex items-center">
          <a href="#consult" style="background-color: black !important;" class="b-btn accent  sm">Contact Us</a>
          <div class="flex sm:hidden items-center"> 
            <label> 
              <input class="b-ch hidden" type="checkbox">
              <div class="flex flex-col ml-[2rem] gap-3"> 
                <div class="w-[3rem] h-[.3rem] bg-black"></div>
                <div class="w-[3rem] h-[.3rem] bg-black"></div>
                <div class="w-[3rem] h-[.3rem] bg-black"></div>
              </div>
              <div class="w-[90%] fixed p-[3rem] z-[10000] bg-white pt-[5rem] shadow-md h-screen top-0"> 
                <ul class="flex flex-col gap-[2.4rem] pb-[5rem]" @click.prevent="() => {}"> 
                  <li><a href="#" class="b-nav-item block w-full">Home</a></li>
                  <li><a href="#services" class="b-nav-item block w-full">Our Services</a></li>
                  <li><a href="#about" class="b-nav-item block w-full">About Us</a></li>
                  <li><a href="#testimonials" class="b-nav-item block w-full">Testimonial</a></li>
                </ul>
              </div>
            </label>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '~/type';
const props = defineProps<{ data?: WizardResponse }>()

const logo = computed(() => props.data?.agency_wizard.website_details.logo || '/img/logo.svg');

const nav = ref<HTMLDivElement>();

onMounted(() => {  
  window.onscroll = function() {
    // pageYOffset or scrollY
    if (window.pageYOffset > 0) {
      nav.value?.classList.add('scrolled')
    } else {
      nav.value?.classList.remove('scrolled')
    }
  }
})
</script>

<style> 
.scrolled {
  background-color: white;
  color: black !important;
  box-shadow: 1px 0px 5px rgba(0, 0, 0, 0.15);
}

.scrolled img {
  filter: invert(1);
}
</style>