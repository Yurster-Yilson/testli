<template>
  <div id="app" class="container text-center pt-5">
<!--    <button @click="show = !show">Toggle</button>-->
<!--    <transition name="ma" appear> &lt;!&ndash;:duration="{enter: 1500, leave: 2000}"&ndash;&gt;-->
<!--    <p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab, ut.</p>-->
<!--    </transition>-->
<!--    <transition-->
<!--      enter-active-class="animated shake"-->
<!--      leave-active-class="animated rollOut"-->
<!--    >-->
<!--      <p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam, eos?</p>-->
<!--    </transition>-->
<!--    <transition name="ma" mode="out-in">-->
<!--      <div v-if="show" key="succes">Succes</div>-->
<!--      <div v-else key="danger">Danger</div>-->
<!-- <p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repellat.</p>&ndash;&gt;-->
<!--    </transition>-->
<!--    <transition-->
<!--    @before-enter="beforeEnter"-->
<!--    @enter="enter"-->
<!--    @after-enter="afterEnter"-->
<!--    @enter-cancelled="enterCancelled"-->

<!--    @before-leave="beforeLeave"-->
<!--    @leave="leave"-->
<!--    @after-leave="afterLeave"-->
<!--    @leave-cancelled="leaveCancelled"-->
<!--    >-->
<!--            <p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repellat.</p>-->
<!--    </transition>-->
      <button @click="add">Add</button>
      <button @click="remove">Remove</button>
    <hr>
    <transition-group tag="ul" name="ma">
      <li v-for="item in items" :key="item">{{item}}</li>
    </transition-group>
  </div>
</template>

<script>

export default {
    data () {
    return{
      items: [1,2,3,4,5],
      nextNum: 6
    }
  },
  methods:{
    add(){
        this.items.splice(this.getIndex(), 0, this.nextNum++)
    },
    remove(){
        this.items.splice(this.getIndex(), 1)
    },
    getIndex(){
        return Math.floor(Math.random() * this.items.length)
    }
    // beforeEnter(el){
    //
    // },
    // enter(el, done){
    //   done()
    // },
    // afterEnter(el){
    //
    // },
    // enterCancelled(el){
    //
    // },
    // beforeLeave(el){
    //
    // },
    // leave(el, done){
    //done()
    // },
    // afterLeave(el){
    //
    // },
    // leaveCancelled(el){
    //
    // },
  }

}
</script>

<style scoped>
/*#app{*/
/*  text-align: center;*/
/*}*/
.ma-enter, .ma-leave-to{
  transform: translateX(-100px);
}
.ma-enter-active, .ma-leave-active {
  transition: all 1s;
}

  @keyframes ma-slide {
    from{
      transform: translateX(0px);
    }
    to{
      transform: translateX(-100px);
    }
  }
</style>
