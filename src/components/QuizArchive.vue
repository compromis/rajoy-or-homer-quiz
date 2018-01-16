<template>
  <div class="quiz-archive">
    <ul>
      <li v-for="quiz in quizzes">
        <a :href="quiz.url">
          <img :src="quiz.thumbnail" :alt="quiz.name" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'quiz-archive',

  data () {
    return {
      quizzes: []
    }
  },

  mounted () {
    axios.get('https://compromis.net/quiz/quizzes.php')
      .then((quizzes) => {
        console.log(quizzes.data)
        this.quizzes = quizzes.data
      })
  }
}
</script>

<style lang="scss" scoped>
@import '../variables';

.quiz-archive {
  position: fixed;
  top: 52px;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.75);
}
</style>
