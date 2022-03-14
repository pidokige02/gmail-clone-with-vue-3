<template>
  <div class="modal">
    <div class="overlay" @click="emit('closeModal')"></div>
    <div class="modal-card">
      <slot />
    </div>
  </div>
</template>

<script>
  // import { onBeforeUnmount } from 'vue'
  import useKeydown from '../composables/use-keydown';

  export default {
    setup(props, {emit}) {
      // let onKeydown = (event) => {
      //   console.log(event.key)

      //   if(event.key == 'Escape') {
      //     emit('closeModal')
      //   }
      // }

      // window.addEventListener('keydown', onKeydown)
      // onBeforeUnmount(()=>{
      //   window.removeEventListener('keydown', onKeydown)
      // })

      useKeydown([
        {key: 'Escape', fn: () => { emit('closeModal') }},
      ])

      return {
        emit
      }
    }
  }
</script>

<style scoped>

</style>