<template> <!--Template 안에는 html 코드-->
  <div><!--Vuejs3 부터는 가장 밖에 있는 div 생략 가능-->
    <h1 class="name">{{name.tag}}</h1>
    <button 
    
    class="btn btn-warning"
    v-on:click="updateName"
    
    >Click!</button>
    <h2 class="title">{{title}}</h2>
    <h2 class="greeting">{{greeting('LiLi')}}</h2>
    <h2 class="greet">{{greet}}</h2>

  </div>
</template>

<script> 
import {reactive} from 'vue';
// import {ref} from 'vue';

export default {
  setup() {
    const name = reactive({
      id: 1,
      tag: "kidcat vue"
    });

    // const name = ref({
    //   id: 1,
    //   name: "kidcat vue"
    // });


    const title = 'Made In Kidcat Nyantopia';

    const greeting = (name) => {
      return 'Hello, ' + name;
    };

    const greet = greeting('LaLa');

    const updateName= () => {
      name.tag="KIDCAT VUE";
      name.id=2;
      console.log(name);
    }

    // const updateName= () => {
    //   name.value.tag="kidcat vue3";
    //   name.value.id=2;
    //   console.log(name);
    // }


    

    return  {
      name,
      title,
      greeting,
      greet,
      updateName
    };



  }
}
</script>

<style> 
  .name {
    color: red;
  }

  .title {
    text-decoration: underline;
  }
</style>

