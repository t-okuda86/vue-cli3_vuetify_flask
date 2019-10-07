<template>
  <div class="home">
    <HeaderComponent title="ホーム" />
    <Part1 />
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderComponent from '@/components/HeaderComponent.vue'
import Part1 from '@/components/Part1.vue'


export default {
  name: 'home',
  components: {
    HeaderComponent,
    Part1
  }
}
</script>
