<template>
  <section class="intro container">
    <p><span class="intro-flair">QUIZ</span></p>
    <h3 class="intro-heading">Mariano Rajoy o Homer Simpson?</h3>
    <p class="intro-description">Ets dels qui pensen que només els “cunyaos” són carnassa de fake news i que estàs prou informat per a diferenciar entre una notícia falsa i una que no ho és? Posa't a prova en el següent quiz!</p>
    <p class="intro-action"><a href="#q1" v-scroll-to="'#q1'">Comença</a></p>
  </section>
</template>

<script>
export default {
  name: 'quiz-intro'
}
</script>

<style lang="scss" scoped>
@import '../variables';

.intro {
  padding: 2.5rem;
  text-align: center;
}

.intro-heading {
  font-family: $font-intro;
  color: $secondary-color;
  font-size: 4rem;
  position: relative;
  text-shadow: 4px 4px 0 black;
  line-height: 1.25;
  margin: 2rem 0;
}

.intro-subheading {
  font-size: 2rem;
  letter-spacing: -1px;
  margin-top: 3rem;
  line-height: 1;
}

.intro-flair {
  border: 1px $text-color solid;
  padding: 0.25rem 1rem;
  border-radius: 20px;
  opacity: 0.75;
}

.intro-icons {
  max-width: 400px;
  margin: 0.5rem auto -2.5rem auto;

  .intro-icon-true svg {
    width: 53px;
  }

  .intro-icon-false svg {
    width: 50px;
  }

  svg {
    width: 100px;
  }
}

.intro-description {
  max-width: 700px;
  margin: 1rem auto;
}

.intro .intro-note {
  font-size: 1rem;
  opacity: 0.5;
  strong {
    color: #fff;
  }
}

.intro-action {
  margin-top: 2rem;

  a {
    color: $text-color;
    border: 2px $text-color solid;
    border-radius: 30px;
    padding: 0.5rem 2rem;
    transition: 0.25s ease-in-out;

    &:hover {
      background: $text-color;
      color: $background;
    }
  }
}

@media (min-width: 769px) {
  .intro {
    padding: 3rem 5rem;

    &-heading {
      font-size: 7rem;
    }

    &-subheading {
      font-size: 2.5rem;
    }

    p {
      font-size: 1.25rem;
    }
  }
}

@media (max-height: 700px) {
  .intro {
    padding-top: 2.5rem;

    &-icons {
      display: none;
    }
  }
}
</style>
