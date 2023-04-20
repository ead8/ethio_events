<script setup>

  const city=ref('')
  const cityError=ref(false)

  const handleSearch=()=>{
    if(city.value==''){
      return cityError.value=true
    }
    navigateTo(`/city/${city.value}/event`)
   
  }

</script>

<template>
    <div
          class="font-serif md:w-[70%] w-[90%] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto"
        >
          <input
            type="text"
            class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
            placeholder="Search by city..." 
            v-model="city"

            :class="cityError?'border-red-500 border':''" 
          />
          <button @click="handleSearch" class="bg-sky-500 px-10 text-white">Search</button>
        </div>
</template>