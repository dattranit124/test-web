<template>
  <div id="app">
    <div v-show="screen == 'test'">
      <Test :question="questions[current]" />
      <div>
        <button class="btn btn-primary m-3" v-show="current>0" @click="current--">PREV</button>
        <button class="btn btn-primary m-3" v-show="current<questions.length-1" @click="current++">NEXT</button> <br>
        <button class="btn btn-primary m-3 " v-show="current == questions.length-1" @click="screen = 'result'" > Nộp bài</button>
      </div>
    </div>
    <div v-show="screen == 'result'">
      <Result :questions = "questions"/>
    </div>
  </div>
</template>

<script>
import Test from './components/Test.vue'
import Result from './components/Result.vue'
export default {
  

  components: {
    Test,Result
  },
  data() {
    return {
      screen : 'test',
      current  : 0,
      questions : [
        {
          content: 'Viet Nam co bao nhieu tinh ? ',
          answers : [
            '64','63','62','65'
          ],
          correctAnswer:1,
          point  : 100,
          answer : null
        },
        {
          content: 'Đặc sản Hưng Yên ? ',
          answers : [
            'Nhãn','Gà','Vải','Mật ong'
          ],
          correctAnswer:0,
          point  : 100,
          answer : null
        },
        {
          content: 'Hôm nay là ngày mấy ',
          answers : [
            '21','22','23','24'
          ],
          correctAnswer:1,
          point  : 100,
          answer : null
        },
        {
          content: 'Thủ đô của Việt Nam ',
          answers : [
            'Hanoi','TPHCM','HY','Hanam'
          ],
          correctAnswer:0,
          point  : 100,
          answer : null
        },
      ]
    }
  }
}
</script>

<style>

</style>
