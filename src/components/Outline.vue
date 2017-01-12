<template>
  <div class="outline">
    <div class="intro">
      <img class="picture" src="./../assets/photo.jpg">
      <h1>{{ basics.name }}</h1>
      <p>{{ basics.label }}</p>
    </div>
    <section>
        <div class="break-section">
          <h1>Personal Info</h1>
        </div>
        <h2>Skype</h2>
        <p>{{ basics.skype }}</p>
        <h2>E-mail</h2>
        <p>{{ basics.email }}</p>
        <h2>Phone</h2>
        <p>{{ basics.phone }}</p>
    </section>
    <section>
      <div class="break-section">
        <h1>Social media</h1>
      </div>
      <div v-for="profile in basics.profiles">
        <h2>{{ profile.network }}</h2>
        <p>{{ profile.url }}</p>
      </div>
    </section>
    <section>
      <div class="break-section">
        <h1>Skills</h1>
      </div>
      <div v-for="skill in skills">
        <h2>{{ skill.name }}</h2>
        <p>{{ skill.level }}</p>
        <progress></progress>
        <span v-for="tech in skill.keywords">
          {{ tech }},
        </span>
      </div>
    </section>
    <section>
      <div class="break-section">
        <h1>Languajes</h1>
      </div>
      <p v-for="language in languages">{{ language.name }} - {{ language.level }}</p>
    </section>
  </div>
</template>

<script>
    import data from '../../static/data.json';

    export default {
      name: 'outline',
      data() {
        return data;
      }
    };
</script>

<style lang="scss" scoped>
  @import "../assets/css/main";

    .outline {
      background-color: $color-primary;
      font-size: 1.5em;
      color: $color-font-primary;
      width: 100%;
      padding-top: 15px;
      padding-bottom: 15px;

      @include respond-to('medium') {
        font-size: 1em;
        width: 25%;
        float: left;
      }
    }

    .intro {
      text-align: center;
      padding-left: 2%;
    }

    .picture {
      display: block;
      margin: 0 auto;
      border-radius: 50%;
      width: 40%;
    }

    section {

      .break-section {
        width: 100%;
        background-color: $color-secundary;
        padding-left: 4%;
        padding-top: 15px;
        padding-bottom: 15px;
      }

      h1 {
        font-weight: bold;
        font-size: 1.5em;
        margin: 0;
      }

      h2 {
        font-weight: bold;
        font-size: 1em;
        padding-left: 4%;
      }

      p {
        padding-left: 4%;
      }

    }

</style>
