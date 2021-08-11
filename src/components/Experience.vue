<template lang='pug'>
  #experience
    v-img(src='@/assets/experience.svg', contain='', eager='',
      lazy-src='@/assets/experience.svg')
    main
      v-container
        v-img.ma-auto.section-profile.mt-5(src='@/assets/education.svg',
          lazy-src='@/assets/education.svg')
        p.header.text-center Education
        v-card.pt-2.pb-5(color='#fbf7f5', flat='', tile='')
          v-card-title.card-header Purdue University
          v-card-subtitle.card-subheader.pt-0.pb-0
            | Bachelor of Science (2018 - 2021)
          v-card-text.card-description.pt-0.pb-0 Computer Science
          v-card-text.card-description.pt-0 3.58 GPA
        v-divider
        v-img.ma-auto.section-profile.mt-5(src='@/assets/work-experience.svg',
          lazy-src='@/assets/work-experience.svg')
        p.header.text-center Work Experience
        template(v-for='(entry, i) in entries')
          WorkEntry(:work='entry')
        v-divider
        v-img.ma-auto.section-profile.mt-5(src='@/assets/skills.svg',
          lazy-src='@/assets/skills.svg')
        p.header.text-center Skills
        v-spacer
        v-subheader.card-subheader(v-for='(skill, i) in skills')
          | {{ skill }}
</template>

<script>
import WorkEntry from '@/components/experience-components/WorkEntry';

export default {
  name: 'Experience',
  components: {
    WorkEntry,
  },
  data() {
    return {
      search: '',
      entries: [
        {
          company: 'Atlassian - Bitbucket',
          title: 'Software Engineer Intern',
          dates: {
            startDate: 'May 2021',
            endDate: 'August 2021',
          },
          overview: `Created feature for repository admins to define
          a default branch deletion behavior for when branches are merged.`,
          skills: [
            'React and Python full coverage testing',
            'Designing maintainable workflows',
            'Refining project scope and estimating project needs',
            'Writing documentation for customers to learn about new feature',
          ],
        },
        {
          company: 'Google',
          title: 'Software Engineer Intern',
          dates: {
            startDate: 'May 2020',
            endDate: 'August 2020',
          },
          overview: `
            Instrumented Node.js and Python Google Cloud Pub/Sub
            client libraries with OpenTelemetry tracing.
          `,
          skills: [
            'Speaking with stakeholders to determine project requirements.',
            `Creating design document with clear objective,
            design decisions, and implementation details.`,
            'Writing easily readable and maintainable code.',
            'Writing full code coverage tests.',
            'Contributing to an open source library.',
          ],
          links: [
            {
              description: 'Google Cloud Medium Blog Post',
              link: 'https://medium.com/google-cloud/integrating-opentelemetry-into-cloud-pub-sub-19aacd83692a',
            },
          ],
        },
        {
          company: 'ITaP Research Computing at Purdue University',
          title: 'Student Systems Administrator',
          dates: {
            startDate: 'September 2018',
            endDate: 'Present',
          },
          overview: `Designed and implemented inventory tracking system
          to aid in deployment of new NSF supercomputer cluster.`,
          skills: [
            `Working with systems engineers to determine useful
            tools and features.`,
            'Writing maintainable code for software integrations.',
          ],
        },
        {
          company: 'Oak Ridge National Laboratory',
          title: 'Software Engineer Intern',
          dates: {
            startDate: 'May 2019',
            endDate: 'August 2019',
          },
          overview: `Integrated user account features from Ruby on Rails
          application into Vue.js application.`,
          skills: [
            `Design and implement APIs to transfer user information
            between applications.`,
            'Create front end interface to update user information.',
            'Write tests for use with Jenkins continuous integration.',
          ],
        },
        {
          company: 'Oak Ridge National Laboratory',
          title: 'Software Engineer Intern',
          dates: {
            startDate: 'May 2018',
            endDate: 'August 2018',
          },
          overview: `Designed video conferencing scheduling tool
          for Ember.js application.`,
          skills: [
            `Work with full time staff to design backend to allow
            for external user authentication.`,
            `Create Ember.js application with a scheduling interface
            to submit video conferencing time slots to database.`,
            'Write mocha unit tests.',
          ],
        },
      ],
      skills: [
        'JavaScript',
        'TypeScript',
        'HTML',
        'CSS',
        'Python',
        'Git',
        'Vue.js',
        'React.js',
      ],
    };
  },
};
</script>

<style lang='scss'>
#experience, #skills-card, #skills-table {
  background-color: #fbf7f5;
  font-family: 'IBM Plex Sans Condensed', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
}

#skills-table {
  tbody {
    tr:hover {
      background-color: #e2dedc;
    }
  }
}
</style>
