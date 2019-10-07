<template>
  <div class="about">
    <HeaderComponent title="このサイトについて"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderComponent from '@/components/HeaderComponent.vue'

export default {
  name: 'about',
  components: {
    HeaderComponent
  }
}
</script>
