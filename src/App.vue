<template>
<!-- This template should give enough examples of what Vue components should look like.-->
<!-- Notable example sections should have comments to help anyone new to the system understand them. -->
<iowa-bar
  iowa_bar_classes="iowa-bar--narrow"
/>

<!-- This is an example of a vertical dots scroll spacer, -->
<!-- Which is what the vertical dots menu will jump to when the corresponding dot is clicked -->
<!-- The ID of the `v-dots-scroll-target` and its corresponding `section_id` in the `sections` array should match -->
<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="hero-banner"></div>
</div>

<banner
  image="/images/widescreen__2592_x_1458/pano.jpg"
  banner_size="large"
  banner_vertical_alignment="vertical-center"
  banner_horizontal_alignment="horizontal-center"
  banner_classes=""
  banner_type="image"
  banner_overlay= "gradient-center"
  banner_text=''
  banner_title='<span>Welcome</span> to Iowa'
  banner_title_classes='headline headline--uppercase'
/>

<div data-uids-cta="data-uids-cta" role="region" class="cta-row__wrapper">
  <div class="cta-row__container">
    <menuGroup
      :items="menu_items"
    />
  </div>
</div>

<verticalDots
  :sections="sections"
/>

<!-- This is a great example of passing `props` in to a component inline. -->
<!-- Anything that will be used as a String in the component can be written without a colon before it. -->
<!-- Anything that does not (eg. Boolean, int, float) must have a colon in front of it. -->
<!-- This tells Vue that it should evaluate it like a javascript variable. -->
<stat
  headline="34"
  headline_prefix="#"
  headline_suffix=""
  stat_description="BEST PUBLIC UNIVERSITY BY U.S. NEWS & WORLD REPORT"
  stat_content="Among the top 2% of universities worldwide."
  :stat_vertical="true"
/>

<!-- This is a great example of passing props from the `data() { return { PROPS }}` area further down in this file.-->
<!-- You can define props there to pass to any component. -->
<!-- However, you must prefix every component used this way with a colon. -->
<statWrapper
  :stats="stats_1"
/>

<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="academic-opportunities"></div>
</div>
<grid-panel
  link_url= 'https://admissions.uiowa.edu/academics/academics'
  image= '/images/viewbook/sections/0315.jpg'
  headline= 'We Work <span>Together</span>'
  button_text= 'View Academic Opportunities'
  button_link= 'https://admissions.uiowa.edu/academics/academics'
  grid_panel_type= 'grid-panel grid-panel--asymmetrical'
  grid_panel_first_column= 'grid-panel__column-image-left'
  grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
  grid_content_position= 'second'
  grid_panel_content= '<p>The University of Iowa blends big-school opportunities with close, personal support to help you excel. We remove the barriers between arts and science, between students and faculty—but most of all, between you and anything you’d like to explore.</p>'
  grid_panel_content_2= '<p>How many universities have both a state-of-the-art children’s hospital and a 3,883-pipe Klais organ? Or helped build the Voyager I satellite and the very first creative writing degree program? Just one: Iowa.</p>'
/>



<footerSection
  :contact_info="contact_info"
  :social_media_links="social_media_links"
/>

</template>

<script>
// In order to use components, you must import them from their files to your script.
// You must also register them in the `components` section of the `export default {}` area below.
// For ease of use, all currently usable components are imported here.
import Banner from './components/Banner.vue';
import Stat from './components/Stat.vue';
import statWrapper from './components/statWrapper.vue';
import IowaBar from './components/IowaBar.vue';
import GridPanel from './components/GridPanel.vue';
import Headline from './components/Headline.vue';
import verticalDots from './components/verticalDots.vue';
import verticalDotsLandmark from './components/verticalDotsLandmark.vue';
import linkButton from './components/linkButton.vue';
import Aerial from './components/Aerial.vue';
import menuGroup from './components/menuGroup.vue';
import footerSection from './components/footerSection.vue';
import Modal from './components/Modal.vue';

export default {
  name: 'App',

  // In addition to importing all components from their files, you must register them here for them to work.
  components: {
    Banner,
    Stat,
    statWrapper,
    IowaBar,
    Headline,
    verticalDots,
    verticalDotsLandmark,
    GridPanel,
    linkButton,
    Aerial,
    menuGroup,
    Modal,
    footerSection
  },

  // This area is where we are currently importing the set props for our components.
  data() {
    return {
      stats_1: [
        {
          headline: '34',
          headline_prefix: '#',
          headline_suffix: '',
          stat_description: 'BEST PUBLIC UNIVERSITY BY U.S. NEWS & WORLD REPORT',
          stat_content: 'Among the top 2% of universities worldwide.',
        },
        {
          headline: '15:1',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'STUDENT-TO-FACULTY RATIO',
          stat_content: 'Get to know your professors.',
        },
        {
          headline: '23',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'INTERNATIONAL FULBRIGHT SCHOLARS IN 2020',
          stat_content: 'That’s the same as some Ivy League schools.',
        },
        {
          headline: '1 in 3',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'UNDERGRADS PARTICIPATE IN RESEARCH',
          stat_content: 'Gain experience now.',
        }
      ],
      menu_items: [
        {
          text: 'Apply Now',
          url: 'https://admissions.uiowa.edu/apply/first-year-student-application-process',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--apply'
        },
        {
          text:  'Schedule a Visit',
          url: 'https://admissions.uiowa.edu/visit-campus',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--visit'
        },
        {
          text: 'Contact Us',
          url: 'https://admissions.uiowa.edu/contact-us',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--ask'
        },
        {
          text: 'Request Information',
          url: 'https://www.maui.uiowa.edu/maui/pub/admissions/webinquiry/undergraduate.page',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--connect'
        },
      ],
      sections: [
        {
          section_title: 'Back to Top',
          section_id: 'hero-banner'
        },
        {
          section_title: 'Academic Opportunities',
          section_id: 'academic-opportunities'
        },
      ],
      contact_info: '<p>Iowa City, Iowa 52242<br><a href="tel:319-335-3847"><i class="fas fa-phone"></i> 319-335-3847</a><br /></p>',
      social_media_links: [
        {
          text: 'Facebook',
          url: 'http://www.facebook.com/admissions.office',
          icon_class: 'fab fa-facebook-square'
        },
        {
          text: 'Instagram',
          url: 'http://instagram.com/iowaadmissions',
          icon_class: 'fab fa-instagram'
        },
        {
          text:  'Twitter',
          url: 'https://twitter.com/iowaadmissions',
          icon_class: 'fab fa-twitter-square'
        },
        {
          text: 'Youtube',
          url: 'http://www.youtube.com/uiowaadmissions',
          icon_class: 'fab fa-youtube'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
$imgpath: '../node_modules/@uiowa/uids/src/assets/images';
@import '../node_modules/@uiowa/uids/src/assets/scss/reset.scss';
@import '../node_modules/@uiowa/uids/src/components/typography/lists/lists.scss';
@import '../node_modules/@uiowa/uids/src/components/tables/tables.scss';
@import '../node_modules/@uiowa/uids/src/components/typography/paragraph/paragraph.scss';
@import '../node_modules/@uiowa/uids/src/components/colors/colors.scss';
@import '../node_modules/@uiowa/uids/src/components/grid/grid.scss';
@import '../node_modules/@uiowa/uids/src/components/viewbook/grid-panel/grid-panel.scss';
@import '../node_modules/@uiowa/uids/src/components/card/card.scss';
@import '../node_modules/@uiowa/uids/src/components/layouts/viewbook/viewbook.scss';

.image-grid__section {
  line-height: 0;
}

.element--circle-list ul {
  margin-top: 1.05rem;
  margin-bottom: 1.05rem;
  margin-left: 1.875rem;
}

// Override and condense for smaller devices.
.cta-row__wrapper {
  transition: padding 0.5s ease;
  padding: 0.3rem 0;
  .cta-row__container .menu a {
    transition: margin 0.5s ease;
    margin: 0px .5rem;
    padding-bottom: 0.5rem;
  }
  .bttn--outline {
    border: none;
  }
}
@media (min-height: 1000px) {
  .cta-row__wrapper {
    padding: 1.875rem 0;
    .cta-row__container .menu a {
      margin: 0px 1.05rem;
    }
    .bttn--outline {
      border: 1px solid rgb(21, 21, 21);
    }
  }
}
</style>
