<!-- components/ServiceCard.vue -->
<template>
    <main class="my-20">
  <div class="flex justify-center items-center flex-col">
    <div data-aos="flip-left" class="inline-block px-4 py-2.5 mb-6 bg-gray-100 rounded-full">
        <span class="text-green-500 font-medium">Our services</span>
      </div>
      
      <h1 data-aos="fade-up" class="text-2xl max-w-sm mx-auto text-center font-medium text-gray-900 mb-4 -mt-2">
        Solutions we provide across different aspect of transportation.
      </h1>
      
      <p data-aos="fade-up" class="text-gray-600  mb-16 max-w-sm mx-auto text-center">
        Discover the unparalleled benefits of our services and elevate your travel experience with us today!
      </p>
  </div>
      <section class="grid grid-cols-1 lg:grid-cols-2 p-4 lg:p-0 gap-6 max-w-7xl mx-auto">
    <div v-for="(item, idx) in servicesInfo" :key="idx" class="group relative w-full rounded-3xl bg-white border border-gray-50 overflow-hidden transition-all duration-300 cursor-pointer">
      <!-- Default State -->
      <div class="relative">
        <!-- Image Container -->
        <div class="h-[300px] overflow-hidden">
          <img 
            :src="item.image" 
            alt="Daily Shuttle" 
            class="w-full h-full object-cover"
          />
        </div>
        
        <!-- Text Content -->
        <div class="p-6">
         <div class="flex justify-between items-center mb-3">
            <h3 class="text-2xl font-semibold">{{ item.title ?? 'Nil' }}</h3>
            <img src="@/assets/icons/green-arrow.svg" class="h-3 w-3" />
         </div>
          <p class="text-gray-500 font-light text-lg">
            {{ `${item.description.length > 20 ? `${item.description.slice(0, 80)}...` : item.description }` ?? 'Nil' }}
          </p>
        </div>
      </div>
  
      <!-- Hover State Overlay -->
      <div :style="{ backgroundColor: item.bgCode }" class="absolute inset-0 translate-y-full opacity-0 transition-all duration-300 ease-out group-hover:translate-y-0 group-hover:opacity-100">
        <div class="p-6 h-full flex flex-col">
          <!-- Icon -->
          <div class="mb-4">
            <div class="w-12 h-12 bg-white/10 rounded-xl flex items-center justify-center">
              <svg 
                class="w-6 h-6 text-white" 
                viewBox="0 0 24 24" 
                fill="currentColor"
              >
                <path d="M20 6H4V4h16v2zm0 4H4v2h16v-2zm0 4H4v2h16v-2zm0 4H4v2h16v-2z"/>
              </svg>
            </div>
          </div>
  
          <!-- Text Content -->
          <h3 class="text-2xl font-semibold text-white mb-4">
            {{ item.title ?? 'Nil' }}
          </h3>
          <p class="text-white/90 mb-8 text-xl">
            {{ item.description ?? 'Nil' }}
          </p>
  
          <!-- Button -->
          <button class="mt-auto bg-gray-25 text-gray-800 px-6 py-2.5 rounded-xl font-medium text-sm w-fit hover:bg-white/90 transition-colors">
            Learn More
          </button>
        </div>
      </div>
    </div>
   </section>
    </main>
  </template>
  
  <script setup lang="ts">
  import image1 from '@/assets/img/shuttlers-bussiness.png'
    import image2 from '@/assets/img/daily-shuttle.jpeg'
      import image3 from '@/assets/img/vehicle-rental.webp'
        import image4 from '@/assets/img/event-go.webp'

  const servicesInfo = ref([
     {
        image: image1,
        bgCode: '#4B44F4',
        title: 'Shuttlers for Business',
        description: `Help employees get to work safely, comfortably, and on time. Here's an employee perk that actually matters every day.`,
        icon: ''
     },{
        image: image2,
         bgCode: '#ADD8E6',
        title: 'Daily Shuttle',
        description: 'Experience the efficiency and convenience of Scheduled Mass-Transit, your dependable solution for seamless, punctual, and eco-friendly commuting.',
        icon: ''
     },
     {
        image: image3,
         bgCode: '#800080',
        title: 'Vehicle Rental',
        description: 'Unlock the freedom to go anywhere, anytime with our Vehicle Rental service. Discover a wide range of options to suit your travel needs and explore the world on your terms.',
        icon: ''
     },
     {
        image: image4,
         bgCode: '#008000',
        title: 'EventGo',
        description: 'Elevate your event experience with our convenient vehicle booking service. Whether you need transportation for weddings, corporate gatherings, or special occasions, simplify your event logistics with ease.',
        icon: ''
     }
  ])
  // No additional logic needed for this component
  </script>
  
  <style scoped>
  /* Custom styles for smoother animations */
  .group:hover .group-hover\:translate-y-0 {
    transform: translateY(0);
  }
  
  .group:hover .group-hover\:opacity-100 {
    opacity: 1;
  }
  </style>
