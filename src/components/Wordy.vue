<template>
    <div class="wordy">
      <p>{{ basics.summary }}</p>
      <div class="title-section">
        <h1>Experience</h1>
      </div>
      <section v-for="work in works">
        <h2>{{ work.position }}</h2>
        <span>{{ work.startDate }} - {{ work.endDate }}</span>
        <p>Company: {{ work.company }}</p>
        <ul>
          <li v-for="highlight in work.highlights">{{ highlight }}</li>
        </ul>
      </section>
      <div class="title-section">
        <h1>Education</h1>
      </div>
      <section v-for="degree in education">
        <span>{{ degree.startDate }} {{ degree.endDate }} - </span>
        <span>{{ degree.area }}</span>
        <span>{{ degree.institution }}</span>
      </section>
      <div class="title-section">
        <h1>Professional Projects</h1>
      </div>
      <section v-for="project in projects">
        <h2> Role: {{ project.rol }}</h2>
        <span>{{ project.startDate }} - {{ project.endDate }}</span>
        <p>Project name: {{ project.name }}</p>
        <p>Description: {{ project.description }}</p>
        <p>Client: {{ project.client.country }} - {{ project.client.name }}</p>
        <span>Technologies:</span>
        <span v-for="(tech, index) in project.technologies" v-if="project.technologies.length-1 == index">
          {{tech}}.
        </span>
        <span v-else>{{tech}}, </span>
        <p>Team Size: {{ project.teamSize }}</p>
        <ul>
          <li v-for="highlight in project.highlights">{{ highlight }}</li>
        </ul>
      </section>
      <div class="title-section">
        <h1>Not For Profit Projects</h1>
      </div>
      <section v-for="project in nfpProjects">
        <h2>Project name: {{ project.name }}</h2>
        <p>Description: {{ project.description }}</p>
        <p>Url: {{ project.url }}</p>
        <span>Technologies:</span>
        <span v-for="(tech, index) in project.technologies" v-if="project.technologies.length-1 == index">
          {{tech}}.
        </span>
        <span v-else>{{tech}}, </span>
      </section>
      <div class="title-section">
        <h1>Personal Interests</h1>
      </div>
      <section>
        <ul>
          <li v-for="interest in interests">{{ interest }}</li>
        </ul>
      </section>
    </div>
</template>

<script>
    import data from '../../static/data.json';

    export default {
      name: 'wordy',
      data() {
        return data;
      },
    };
</script>

<style lang="scss" scoped>
  @import '../assets/css/main';

  .wordy {
    padding-left: 2%;
    padding-right: 2%;
    padding-top: 15px;
    padding-bottom: 15px;

    p {
      font-size: 1.2em;
    }

    span {
      font-size: 1.2em;
    }
  }

  .title-section {
    border-bottom: solid $color-border;
    border-top: solid $color-border;
    padding-bottom: 15px;
    padding-top: 15px;
    margin-bottom: 15px;

    h1 {
      margin: 0;
      color: $color-primary;
      -webkit-font-smoothing: auto;
      -moz-osx-font-smoothing: auto;
      font-size: 1.6em;
    }
  }

  section {
    margin-bottom: 40px;

    li {
      font-size: 1.1em;
    }
  }

</style>
