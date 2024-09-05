<template>
  <div>
    <h1>This is Home page</h1>
    <!-- <form action=""> -->
      <!-- <InputField :name="name" @update-Name="updateName"/> -->
       <InputField v-model="name"/>
      <br>
      <button @click="updateName">Submit</button>
    <!-- </form>-->
    {{ name }}
  </div>
</template>

<script>

import InputField from '@/components/InputField.vue';

export default{
  components: {
    InputField
  },

  data() {
    return {
      name : 'Kossie Coder'
    }
  },

  beforeCreate(){
    console.log("beforeCreate ",this.name);
    // this.name 에 접근 불가
  },

  created(){
    console.log("created ",this.name); 
    // 서버에 요청을 보내서 응답을 받아온 데이터를 data에 업데이트 해줄때
    // mounted에서 하는 경우도 있음
  },
  beforeMount(){
    alert("beforeMount");
    // DOM이 mount가 안된 상태 body 비어있음
  },
  mounted(){
    alert("mounted");
    // body 채워짐 -> 여기서부터 DOM에 접근이 가능하게됨
    // DOM을 컨트롤하고싶으면 mounted에서 하면됨
  },
  beforeUpdate(){
    alert("beforeUpdate");
    // data가 바뀌기전 훅 실행
  },
  updated(){
    alert("updated");
  },
  beforeDestroy(){
    alert("beforeDestroy");
  },
  destroyed(){
    alert("destroyed");
  },

  methods: {
    updateName() {
      this.name = 'hello';
    } 
  }
}
</script>

<style scoped>
h1 {
  color: red;
}
</style>