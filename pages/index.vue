<template>
  <div>
    <HomePageSection sectionId="why-vue" classes="hero bg-dark">
      <div class="col-md-6 col-sm-12">
        <!-- TODO: Fix this styling -->
        <h1>VueScreencasts.com</h1>
        <h3>All things intermediate and advanced</h3>

        <p>Whether you hire us, receive mentorship, or work at your own pace, this is as close to uploading Vue to your brain as it gets.</p>
        <p>Choose a solution:</p>

        <div class="bullet-points">
          <div class="bullet-point">
            <v-btn to="/pro?solution=pro-platinum" color="green accent-2">Hire Me</v-btn>
            <p>Coaching while working with you in the trenches of your project.</p>
          </div>
          <div class="bullet-point">
            <v-btn to="/pro?solution=pro-gold" color="green accent-2">Mentorship</v-btn>
            <p>Custom action plan and regular pair-programming.</p>
          </div>
          <div class="bullet-point">
            <v-btn to="/pro?solution=pro-bronze" color="green accent-2">Quality Learning</v-btn>
            <p>Structured courses and high-quality videos.</p>
          </div>
          <div class="bullet-point">  
            <v-btn to="/courses" color="green accent-2">Free Videos</v-btn>
            <p>200+ free videos because we're cool like that.</p>
          </div>
        </div>
      </div>
      <div class="col-md-6 col-sm-12 d-sm-block d-none center-md">
        <img src="~assets/vuescreencasts-student-learning-3.png" class="img-responsive bottom-image" alt="Happy Vue Programmer">
      </div>
    </HomePageSection>

    <div class="bg-gray">
      <TestimonialsRow :testimonialIds="['99', '87', '21', '1']" class="paper-container-large" />
    </div>
    
    <HomePageSection classes="bg-dark" id="pro-platinum">
      <div class="col-sm-12 center-md">
        <div class="header-section">
          <h2 class="section-title">Platinum Package</h2>
          <h2 class="section-subtitle">When the Survival of your Company or Job is on the line.</h2>
        </div>

        <ProPackageCard :stripePlanId="11" 
                        nextSolutionId="pro-gold"
                        bossLink="https://docs.google.com/document/d/13StavsXklWSzuYk0PN9G9LAja9QfXfwwJQkg3IpRcRU/edit?usp=sharing">
          <p><strong>YOU'RE HIRING ME.  LET'S DO IT NOW.</strong></p>
          <p>I am right there, coding with you in the trenches. I will care about your project as much as you do. I will also coach you and make you succeed.</p>
          <p>Imploding projects? Impossible deadlines?</p> 
          <p>Hire me and let's get started.</p>
        </ProPackageCard>
      </div>
    </HomePageSection>

    <div class="bg-gray">
      <TestimonialsRow :testimonialIds="['4', '96', '76', '98']" class="paper-container-large" />
    </div>
    
    <HomePageSection class="bg-dark" id="pro-gold">
      <div class="col-sm-12 center-md">
        <div class="header-section">
          <h2 class="section-title">Gold Package</h2>
          <h2 class="section-subtitle">Your Best Bet for Fast Growth.</h2>
        </div>

        <ProPackageCard :stripePlanId="10" 
                        nextSolutionId="pro-silver"
                        bossLink="https://docs.google.com/document/d/166C59AXbqgFGSz1iRhwrp-MXUqIkKLCxpplJIcITwyU/edit?usp=sharing">
          <p>You have a clear goal, but that's not enough.</p>
          <p>You also need a specific, detailed action plan that maximizes your learning while respecting your time. Followed up by one-on-one pair-programming sessions to hold you accountable and keep you winning.</p>
          <p>Say goodbye to overwhelm.</p>
          <p>Say hello to growth.</p>
        </ProPackageCard>
      </div>
    </HomePageSection>

    <div class="bg-gray">
      <TestimonialsRow :testimonialIds="['88', '19', '48', '18']" class="paper-container-large" />
    </div>

    <HomePageSection class="bg-dark" id="pro-silver">
      <div class="col-sm-12 center-md">
        <div class="header-section">
          <h2 class="section-title">Silver Plan</h2>
          <h2 class="section-subtitle">Mentorship on a Budget.</h2>
        </div>

        <ProPackageCard :stripePlanId="9" 
                        nextSolutionId="pro-bronze"
                        bossLink="https://docs.google.com/document/d/133lz57ovI0PiD1ZVpT-mcDShQBvmqTb7BHwihFsDB5c/edit?usp=sharing">
          <p>If you're a self-directed learner, or on a budget, but know how important mentorship is - this is a great plan.</p>
          <p>Weekly email check-ins give you the chance to get the guidance you need.</p>
          <p>This is a great way to get started, and remember you can change your plan up or down at any time!</p>
        </ProPackageCard>
      </div>
    </HomePageSection>

    <div class="bg-gray">
      <TestimonialsRow :testimonialIds="['16', '79', '93', '97']" class="paper-container-large" />
    </div>

    <HomePageSection class="bg-dark" id="pro-bronze">
      <div class="col-sm-12 center-md">
        <div class="header-section">
          <h2 class="section-title">Bronze Plan</h2>
          <h2 class="section-subtitle">High-Quality Resources for Self-Directed Learning.</h2>
        </div>

        <ProPackageCard :stripePlanId="8" 
                        nextSolutionId="more-questions"
                        nextSolutionText="More Questions?"
                        bossLink="https://docs.google.com/document/d/16cXGOJkQoqwG-iq4sc0n84KMMldOlNHMGbhTijaPsQk/edit?usp=sharing">
          <p>You like our free videos.  That's why you're here.</p>
          <p>But you know it's time to grow and get serious.</p>
          <p>Our Pro Courses tackle harder subjects, and are designed to level you up.</p>
        </ProPackageCard>
      </div>
    </HomePageSection>

    <div class="bg-gray">
      <TestimonialsRow :testimonialIds="['34', '85', '77', '70']" class="paper-container-large" />
    </div>

    <HomePageSection classes="bg-dark" id="more-questions">
      <div class="col-md-7 col-sm-12">
        <!-- TODO: put this stuff in every section, then replace it with "I care" message and  "how to ask more questions" message  -->
        <h2 class="section-title">Talk to us</h2>
        <p>We've done our best to answer everything, but if you have more questions just email <a href="mailto:jeffrey@vuescreencasts.com" target="_blank">jeffrey@vuescreencasts.com</a> or text <a href="sms:501-256-3078">(501) 256-3078</a> right now.</p>
        <p>There are no stupid questions, and the only way that we can improve is if you let us know if somethig isn't clear.  Reach out - we're here for you.</p>
        <p>Fair enough?</p>
      </div>
      <div class="col-md-5 col-sm-12 d-sm-block d-none center-md">
        <img src="~assets/vuescreencasts-student-coding-2.png" class="img-responsive img-center-xs" alt="Ember School Student Learning">
      </div>
    </HomePageSection>

    <div class="bg-gray">
      <TestimonialsRow :testimonialIds="['8', '11', '104', '100']" class="paper-container-large" />
    </div>
  </div>
</template>

<script>
import TestimonialsRow from '@/components/TestimonialsRow.vue';
import ProPackageCard from '@/components/ProPackageCard.vue';
import HomePageSection from '@/components/HomePageSection.vue';

export default {
  components: {
    TestimonialsRow,
    ProPackageCard,
    HomePageSection,
  },
}
</script>

<style lang="scss">
$font: Roboto, sans-serif;

$indigo: #3F51B5;
$indigo-300: #7986CB;
$indigo-100: #c5cae9;
$orange: #FF6E40;
$grey: #E2E7E9;
$dark-grey: #333;
$navy: #24303C;
$dark-navy: #1A242E;
$green: #23B408;


$blue: #2196f3;
$blue-300: #64b5f6;
$blue-100: #bbdefb;
$blue-50: #E3F2FD;

$transparent-blue: rgba(33, 150, 243, .12);

$primary: $blue;

.bg-gray {
  background-color: #EBEFF2;
}

.bg-white {
  background-color: #ffffff;
}

.vertical-align-items {
  display: flex;
  justify-content: center; /* align horizontal */
  align-items: center;
}

.bullet-points {
  p {
  }
  margin-bottom: 16px;

  .bullet-point {
    margin-bottom: 12px;
    p {
      display: inline-block;
      margin: 4px 0;
      vertical-align: bottom;
    }
  }
}

.bg-dark {
  background-color: #2D384A;
  .section-title {
    color: #ffffff;
  }
  color: #ffffff;
  h2, h3, h4 {
    color: #ffffff;
  }
  .disabled {
    background-color: $grey;
    color: #aaaaaa;
  }
  .check {
    color: $green;
  }
  li a {
    color: #ffffff;
  }

  p a {
    color: #fff;
  }

  .header-section {
    padding: 24px;
    margin-left: -24px;
    background-color: white;
    border-radius: 20px;
    display: inline-block;

    h1, h2, h3, h4 {
      color: #2163B3;
      // color: #2773D3;
      // color: #2D374A;
      // color: #017FFF;

      &.section-title, &.section-subtitle {
        color: #2163B3;
        // color: #2773D3;
        // color: #2D374A;
        // color: #017FFF;
        margin-bottom: 0px;
      }

      &.platinum {
        color: #797979;
      }
      &.gold {
        color: #F8AE00;
      }
      &.silver {
        color: #C0C0C0;
      }
      &.bronze {
        color: #CD7F31;
      }
    }
  }

  .email-signup {
    fieldset {
      border: 2px solid white !important;

      legend {
      }
    }

    input {
      color: white !important;
    }

    .email-field.error--text {
      color: #FAA !important;
      caret-color: #FAA !important;
    }
    .email-field .error--text {
      color: #FAA !important;
    }

    .v-text-field__slot label {
        color: #AAF !important;
    }

    button.theme--light.v-btn--outlined.v-btn {
      color: white !important;
      border-color: white !important;

      &.v-btn--disabled {
        color: grey !important;
        border-color: grey !important;
      }
    }
  }
    
  
}

</style>
