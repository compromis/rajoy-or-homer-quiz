<template>
  <section class="intro container">
    <p><span class="intro-flair">QUIZ</span></p>
    <h3 class="intro-heading">
      <img src="../assets/images/rajoy.jpg" alt="Mariano Rajoy" class="intro-image intro-image-rajoy" />
      <img src="../assets/images/homer.jpg" alt="Homer Simpson" class="intro-image intro-image-homer" />
      <span class="intro-heading-text">
        <span class="intro-heading-text-mariano">Mariano Rajoy</span>
        <span class="intro-heading-text-or">o</span>
        <span class="intro-heading-text-homer">Homer Simpson?</span>
      </span>
    </h3>
    <h2 class="intro-subheading">Qui ho va dir?</h2>
    <p class="intro-description">...</p>
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
  line-height: 1;
  margin: 0 auto 2rem auto;
  position: relative;
  max-width: 1000px;

  &-text {
    position: relative;
    z-index: 20;
  }
}

.intro-image {
  position: absolute;
  top: 50px;
  z-index: 10;
  border: 10px white solid;
  box-shadow: 0 5px 10px -5px rgba(0, 0, 0, 0.5);
  opacity: 0.75;

  &-rajoy {
    left: -120px;
    height: 240px;
    transform: rotate(-10deg);
  }

  &-homer {
    right: -100px;
    height: 240px;
    transform: rotate(10deg);
  }
}

.intro-subheading {
  font-size: 2rem;
  letter-spacing: -1px;
  margin-top: 3rem;
  line-height: 1;
}

.intro-description {
  max-width: 800px;
  margin: 1rem auto;
}

.intro-flair {
  border: 1px $text-color solid;
  padding: 0.25rem 1rem;
  border-radius: 20px;
  opacity: 0.75;
}

.intro-action {
  margin-top: 2rem;

  a {
    background: rgba(161, 211, 243, 0.5);
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
      line-height: 1.1;
    }

    &-subheading {
      font-size: 2.5rem;
    }

    &-image {
      opacity: 1;
    }

    p {
      font-size: 1.25rem;
    }
  }
}

@media (min-width: 1220px) {
  .intro {
    &-heading {
      padding-top: 250px;
    }

    &-image {
      &-rajoy {
        height: 300px;
        left: 200px;
      }

      &-homer {
        height: 300px;
        right: 200px;
      }
    }
  }
}

@media (max-height: 700px) {
  .intro {
    padding-top: 2.5rem;
  }
}
</style>
