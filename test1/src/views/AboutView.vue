<template>
  <div class="about">
    <h1>This is an about page</h1>
    <PjbCoderVue name="sadf">
      <template v-slot:header="props">
        <p id="xx">header111 {{ props.kossie }}</p>
      </template>
      <template #default>
        hello22
      </template>
    </PjbCoderVue>
    <button @click="ggg">
      변경하기
    </button>
    <transition>
      <p v-if="show">hello vue.js!</p>
    </transition>
  </div>
</template>

<script>
import PjbCoderVue from '@/components/PjbCoder.vue'

export default {
  components: {
    PjbCoderVue
  },
  data() {
    return {
      show : true
    }
  }, 
  methods: {
    ggg(){
      this.show = !this.show;
    }
  }
  
}
</script>

<style scoped>
  #xx{
    color: red;
  }

  .v-enter-active, .v-leave-active {
    transition: opacity 1s;
  }

  .v-enter, .v-leave-to {
    opacity: 0;
  }

</style>