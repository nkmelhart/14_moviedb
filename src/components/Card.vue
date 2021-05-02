<template>
  <div class="max-w-full flex">
      <img src="https://via.placeholder.com/200x300.png" alt="Movie Poster">
      <div class="flex flex-col justify-between p-4 leading-normal bg-coolGray-400 border-b border-l border-r border-coolGray-400 rounded-b lg:boarder-l-0 lg-border-t lg:border-coolGray-400 lg:rounded-b-none lg:rounded-r">
      <div class="mb-8">
          <div class="mb-2 text-xl font-bold text-coolGray-900">movie.title</div>
          <p class="text-base text-coolGray-700 line-clamp-6">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
      </div>
      <div class="flex items-start justify-end space-x-4">
          <div class="flex flex-col items-center">
              <button class="text-coolGray-400 hover:text-red-600">
                  <bi:suit-heart-fill class="w-8 h-8"/>
                  <span>0</span>
              </button>
            </div>
            <div class="flex flex-col items-center">
            <button @click="toggle" class="text-coolGray-400 hover:text-blue-600">
                <bx:bxs-message class="w-8 h-8"/>
            </button>
            </div>
      </div>
    </div>
  </div>
  <Comments v-if="value" @close="toggle"/>
</template>

<script>

import Comments from '../components/Comments.vue'
import { useToggle } from '@vueuse/core'

export default {
    name: 'Card',
    components: { Comments },
    setup(){
        const [value, toggle] = useToggle(false)

        return { value, toggle }
    }

}
</script>

<style>

</style>