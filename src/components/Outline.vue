<template>
  <div class="outline">
    <div class="intro">
      <img class="picture" src="./../assets/photo.jpg">
      <h1>{{ basics.name }}</h1>
      <p>{{ basics.label }}</p>
    </div>
    <section>
        <div class="title-section">
          <h1>Personal Info</h1>
        </div>
        <div class="body-section">
          <h2>Skype</h2>
          <p>{{ basics.skype }}</p>
          <h2>E-mail</h2>
          <p>{{ basics.email }}</p>
          <h2>Phone</h2>
          <p>{{ basics.phone }}</p>
        </div>
    </section>
    <section>
      <div class="title-section">
        <h1>Social media</h1>
      </div>
      <div class="body-section" v-for="profile in basics.profiles">
        <h2>{{ profile.network }}</h2>
        <p>{{ profile.url }}</p>
      </div>
    </section>
    <section>
      <div class="title-section">
        <h1>Skills</h1>
      </div>
      <div class="body-section" v-for="skill in skills">
        <h2>{{ skill.name }}</h2>
        <progress-bar :percentage="skill.level"></progress-bar>
        <p class="skill" v-for="tech in skill.keywords">
          {{ tech }}
        </p>
      </div>
    </section>
    <section>
      <div class="title-section">
        <h1>Languajes</h1>
      </div>
      <div class="body-section" v-for="language in languages">
        <p>{{ language.name }} - {{ language.level }}</p>
      </div>
    </section>
  </div>
</template>

<script>
    import data from '../../static/data.json';
    import ProgressBar from './ProgressBar';

    export default {
      name: 'outline',
      data() {
        return data;
      },
      components: {
        ProgressBar
      }
    };
</script>

<style lang="scss" scoped>
  @import "../assets/css/main";

    .outline {
      background-color: $color-primary;
      color: $color-font-primary;
      width: 100%;
      padding-top: 15px;
      padding-bottom: 15px;

      @include respond-to('large') {
        width: 1%;
        max-width: 300px;
        display: table-cell;
      }
    }

    .intro {
      text-align: center;
      padding-left: 2%;

      h1 {
        font-size: 2em;
      }

      p {
        font-size: 1.2em;
      }

      @include respond-to('large') {
        h1 {
          font-size: 1.5em;
        }
      }
    }

    .picture {
      display: block;
      margin: 0 auto;
      border-radius: 50%;
      width: 40%;
    }

    section {
      padding-bottom: 15px;
      padding-top: 15px;

      .title-section {
        width: 100%;
        background-color: $color-secundary;
        padding-top: 15px;
        padding-bottom: 15px;
      }

      .body-section {
        padding-left: 4%;
        padding-right: 4%;
      }

      h1 {
        font-weight: bold;
        font-size: 1.4em;
        margin: 0;
        padding-left: 4%;
      }

      h2 {
        font-weight: bold;
        font-size: 1.3em;
      }

      p {
        font-size: 1.2em;
      }

      .skill {
        font-size: 1em;
        margin: 0;
      }

      @include respond-to('large') {
        padding-bottom: 5px;
        padding-top: 0px;

        .title-section {
          padding-top: 8px;
          padding-bottom: 8px;
        }

        h1 {
          font-size: 1.2em;
        }

        h2 {
          font-weight: bold;
          font-size: 1em;
        }

        p {
          font-size: 1em;
        }

        .skill {
          font-size: 1em;
          margin: 0;
        }
      }
    }

</style>
