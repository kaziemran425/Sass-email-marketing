<template>
  <q-page>
    <div id="home" class="hero-section bg-teal-8 text-white q-pb-xl relative-position">
      <div class="container q-pa-lg text-center text-md-left" style="max-width: 1200px; margin: 0 auto">
        <div class="row items-center q-col-gutter-xl reverse-wrap q-pt-xl">
          <div class="col-12 col-md-6 text-center text-md-left">
            <q-badge color="orange" label="v2.0 Released" class="q-mb-md text-subtitle2 q-pa-sm" />
            <h1 class="text-h3 text-weight-bolder q-mt-none q-mb-md leading-tight">
              The Smartest Way to Manage Email in the World
            </h1>
            <p class="text-h6 text-teal-1 q-mb-lg">
              Designed for global and regional businesses. Create stunning email
              marketing campaigns and deliver them with unparalleled speed.
            </p>
            <div class="row q-gutter-md justify-center justify-md-start">
              <q-btn
                to="/login"
                size="lg"
                color="orange"
                text-color="white"
                label="Get Started Free"
                icon-right="arrow_forward"
                unelevated
                no-caps
                class="text-weight-bold"
              />
              <q-btn to="/" size="lg" outline color="white" label="View Demo" no-caps />
            </div>
          </div>

          <div class="col-12 col-md-6 text-center">
            <q-img
              src="~src/assets/email-marketing.png"
              class="hero-image shadow-20 rounded-borders"
              style="border: 8px solid rgba(255, 255, 255, 0.2)"
            />
          </div>
        </div>
      </div>

      <div class="custom-shape-divider-bottom-1678901234">
        <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
          <path d="M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z" class="shape-fill" fill="#ffffff"></path>
        </svg>
      </div>
    </div>

    <div id="features" class="q-py-xl bg-white" style="max-width: 1200px; margin: 0 auto">
      <div class="text-center q-mb-xl">
        <div class="text-teal-7 text-weight-bold text-uppercase q-mb-sm">Features</div>
        <h2 class="text-h4 text-weight-bold text-grey-9 q-mt-none">Everything you need to grow</h2>
      </div>

      <div class="row q-col-gutter-lg q-pa-md">
        <div class="col-12 col-md-4">
          <q-card flat class="text-center q-pa-md bg-grey-1 rounded-borders" style="height: 100%">
            <q-avatar size="80px" color="teal-1" text-color="teal-7" class="q-mb-md">
              <q-icon name="campaign" size="40px" />
            </q-avatar>
            <div class="text-h6 text-weight-bold q-mb-sm">Automated Campaigns</div>
            <p class="text-grey-7">Set up drip campaigns and automated responses so you make money while you sleep.</p>
          </q-card>
        </div>
        <div class="col-12 col-md-4">
          <q-card flat class="text-center q-pa-md bg-grey-1 rounded-borders" style="height: 100%">
            <q-avatar size="80px" color="orange-1" text-color="orange" class="q-mb-md">
              <q-icon name="people_alt" size="40px" />
            </q-avatar>
            <div class="text-h6 text-weight-bold q-mb-sm">Smart Segmentation</div>
            <p class="text-grey-7">Target the right audience based on their behavior, location, and previous purchases.</p>
          </q-card>
        </div>
        <div class="col-12 col-md-4">
          <q-card flat class="text-center q-pa-md bg-grey-1 rounded-borders" style="height: 100%">
            <q-avatar size="80px" color="teal-1" text-color="teal-7" class="q-mb-md">
              <q-icon name="query_stats" size="40px" />
            </q-avatar>
            <div class="text-h6 text-weight-bold q-mb-sm">Advanced Analytics</div>
            <p class="text-grey-7">Track open rates, click-through rates, and overall ROI in a beautiful visual dashboard.</p>
          </q-card>
        </div>
      </div>
    </div>

    <div class="q-py-xl bg-grey-1">
      <div class="row items-center q-col-gutter-xl q-pa-md" style="max-width: 1200px; margin: 0 auto">
        <div class="col-12 col-md-6 text-center">
          <q-img
            src="~src/assets/email-marketing.png"
            class="hero-image shadow-10 rounded-borders"
            style="border: 4px solid white"
          />
        </div>
        <div class="col-12 col-md-6">
          <div class="text-teal-7 text-weight-bold text-uppercase q-mb-sm">Simple Workflow</div>
          <h2 class="text-h4 text-weight-bold text-grey-9 q-mt-none q-mb-md">Get Compliant in 3 Minutes</h2>
          <p class="text-grey-7 text-body1 q-mb-lg">
            Import your contacts, design your template using our drag-and-drop builder, and hit send. It is that simple to start reaching your audience.
          </p>
          <q-list>
            <q-item>
              <q-item-section avatar><q-avatar color="teal-1" text-color="teal-7" icon="upload_file" /></q-item-section>
              <q-item-section><strong>Step 1:</strong> Import CSV Contacts</q-item-section>
            </q-item>
            <q-item>
              <q-item-section avatar><q-avatar color="teal-1" text-color="teal-7" icon="draw" /></q-item-section>
              <q-item-section><strong>Step 2:</strong> Design Email Template</q-item-section>
            </q-item>
            <q-item>
              <q-item-section avatar><q-avatar color="teal-1" text-color="teal-7" icon="send" /></q-item-section>
              <q-item-section><strong>Step 3:</strong> Schedule & Send</q-item-section>
            </q-item>
          </q-list>
        </div>
      </div>
    </div>

    <div id="pricing" class="bg-white q-py-xl">
      <div class="text-center q-mb-xl" style="max-width: 1200px; margin: 0 auto">
        <h2 class="text-h4 text-weight-bold text-grey-9 q-mt-none">Simple, transparent pricing</h2>
        <p class="text-grey-7 text-h6">Choose the plan that fits your business.</p>
      </div>

      <div class="row q-col-gutter-lg justify-center q-pa-md" style="max-width: 1200px; margin: 0 auto">
        <div class="col-12 col-sm-6 col-md-4">
          <q-card class="rounded-borders q-pa-lg text-center shadow-4">
            <div class="text-h5 text-weight-bold q-mb-md">Starter</div>
            <div class="text-h3 text-teal-7 text-weight-bolder q-mb-md">$19<span class="text-h6 text-grey-6">/mo</span></div>
            <q-list dense class="text-left q-mb-lg text-grey-8">
              <q-item><q-item-section avatar><q-icon name="check" color="teal" /></q-item-section><q-item-section>Up to 2,500 contacts</q-item-section></q-item>
              <q-item><q-item-section avatar><q-icon name="check" color="teal" /></q-item-section><q-item-section>Drag & Drop Builder</q-item-section></q-item>
              <q-item><q-item-section avatar><q-icon name="check" color="teal" /></q-item-section><q-item-section>Basic Analytics</q-item-section></q-item>
            </q-list>
            <q-btn outline color="teal-7" label="Start Free Trial" class="full-width" no-caps />
          </q-card>
        </div>

        <div class="col-12 col-sm-6 col-md-4">
          <q-card class="rounded-borders q-pa-lg text-center shadow-10 bg-teal-8 text-white relative-position">
            <q-badge color="orange" floating label="MOST POPULAR" class="q-pa-xs text-weight-bold" style="top: -10px; right: -10px" />
            <div class="text-h5 text-weight-bold q-mb-md">Professional</div>
            <div class="text-h3 text-weight-bolder q-mb-md">$49<span class="text-h6 text-teal-2">/mo</span></div>
            <q-list dense class="text-left q-mb-lg text-white">
              <q-item><q-item-section avatar><q-icon name="check" color="orange" /></q-item-section><q-item-section>Up to 10,000 contacts</q-item-section></q-item>
              <q-item><q-item-section avatar><q-icon name="check" color="orange" /></q-item-section><q-item-section>Advanced Automations</q-item-section></q-item>
              <q-item><q-item-section avatar><q-icon name="check" color="orange" /></q-item-section><q-item-section>Remove Watermark</q-item-section></q-item>
            </q-list>
            <q-btn unelevated color="orange" text-color="white" label="Get Started" class="full-width" no-caps />
          </q-card>
        </div>
      </div>
    </div>

    <div id="contact" class="bg-grey-2 q-py-xl">
      <div class="row q-col-gutter-xl q-pa-md" style="max-width: 1200px; margin: 0 auto">
        <div class="col-12 col-md-7">
          <div class="text-h4 text-weight-bold q-mb-sm">Get in Touch</div>
          <div class="text-grey-7 text-body1 q-mb-lg">
            Have questions or want to learn more? Get in touch with our team.
          </div>

          <q-form @submit.prevent="submitContactForm" class="q-gutter-y-md">
            <div class="row q-col-gutter-md">
              <div class="col-12 col-sm-6">
                <q-input v-model="contactForm.name" type="text" outlined bg-color="white" placeholder="Full Name" :rules="[val => !!val || 'Name is required']" />
              </div>
              <div class="col-12 col-sm-6">
                <q-input v-model="contactForm.email" type="email" outlined bg-color="white" placeholder="Email Address" :rules="[val => !!val || 'Email is required']" />
              </div>
            </div>

            <q-input v-model="contactForm.subject" type="text" outlined bg-color="white" placeholder="Subject" />
            <q-input v-model="contactForm.message" type="textarea" outlined bg-color="white" placeholder="Your Message..." rows="4" :rules="[val => !!val || 'Message is required']" />

            <div>
              <q-btn type="submit" color="teal-7" size="lg" label="Send Message" :loading="isSending" no-caps />
            </div>
          </q-form>
        </div>

        <div class="col-12 col-md-5 flex flex-center">
          <q-card class="shadow-4 rounded-borders q-pa-md" style="max-width: 350px; width: 100%">
            <q-card-section class="text-center">
              <div class="text-weight-bold text-h6 q-mb-sm">Scan to Chat</div>
              <p class="text-grey-6 text-caption">Connect with our support team instantly on WhatsApp</p>
            </q-card-section>
            <q-card-section class="flex flex-center">
              <q-img src="~src/assets/scan.jpeg" style="width: 200px; height: 200px" class="rounded-borders" />
            </q-card-section>
          </q-card>
        </div>
      </div>
    </div>

    <div class="bg-grey-10 text-grey-4 q-py-lg">
      <div class="row justify-between q-pa-md" style="max-width: 1200px; margin: 0 auto">
        <div class="col-12 col-md-4 q-mb-md text-center text-md-left">
          <div class="text-h6 text-white text-weight-bold q-mb-sm">Email Marketing SaaS</div>
          <p class="text-body2">
            Helping businesses connect with their audience through beautifully
            crafted, intelligent email campaigns.
          </p>
        </div>
        <div class="col-12 col-md-4 text-center text-md-right">
          <q-btn flat round color="white" icon="facebook" />
          <q-btn flat round color="white" icon="fab fa-twitter" />
          <q-btn flat round color="white" icon="fab fa-linkedin" />
          <div class="q-mt-sm text-caption">
            © 2026 SaaS Inc. All rights reserved.
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useQuasar } from 'quasar';

const $q = useQuasar();

// Reactive form data
const contactForm = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
});

const isSending = ref(false);

// Load saved draft from Local Storage when page mounts
onMounted(() => {
  const savedForm = localStorage.getItem('contact_form_draft');
  if (savedForm) {
    try {
      contactForm.value = JSON.parse(savedForm);
    } catch (e) {
      console.error("Could not parse saved form data");
    }
  }
});

// Function to handle form submission
const submitContactForm = async () => {
  isSending.value = true;

  // Simulate an API call delay
  await new Promise(resolve => setTimeout(resolve, 1000));

  // Save successful submission to local storage
  localStorage.setItem('last_contact_submission', JSON.stringify(contactForm.value));

  // Clear the draft
  localStorage.removeItem('contact_form_draft');

  $q.notify({
    type: 'positive',
    message: 'Message sent successfully! Our team will contact you soon.',
    position: 'top'
  });

  // Reset form
  contactForm.value = { name: '', email: '', subject: '', message: '' };
  isSending.value = false;
};
</script>

<style scoped>
.custom-shape-divider-bottom-1678901234 {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
}

.custom-shape-divider-bottom-1678901234 svg {
  position: relative;
  display: block;
  width: calc(100% + 1.3px);
  height: 60px;
}
</style>
