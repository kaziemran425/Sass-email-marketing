<template>
  <q-page class="window-height window-width row justify-center items-center bg-teal-1 q-pa-sm q-pa-md-md">
    <q-card class="rounded-borders shadow-8 full-width" style="max-width: 450px">
      <q-card-section class="text-center q-pt-md q-pt-sm-xl q-pb-sm">
        <q-avatar size="70px" color="orange" text-color="white" class="q-mb-sm shadow-3">
          <q-icon name="mail" />
        </q-avatar>

        <div class="text-h5 text-weight-bold text-grey-9">
          {{ isLogin ? "Welcome Back" : "Create an Account" }}
        </div>
        <div class="text-subtitle2 text-grey-6 q-mt-xs">
          {{ isLogin ? "Sign in to access your dashboard" : "Start your email marketing journey" }}
        </div>
      </q-card-section>

      <q-card-section class="q-px-md q-px-sm-lg">
        
        <q-form v-if="isLogin" @submit.prevent="handleLogin" class="q-gutter-y-md">
          <q-input
            v-model="email"
            label="Email Address"
            type="email"
            outlined
            lazy-rules
            :rules="[(val) => !!val || 'Email is required']"
          >
            <template v-slot:prepend>
              <q-icon name="email" color="teal-7" />
            </template>
          </q-input>

          <q-input
            v-model="password"
            label="Password"
            :type="showPassword ? 'text' : 'password'"
            outlined
            lazy-rules
            :rules="[(val) => !!val || 'Password is required']"
          >
            <template v-slot:prepend>
              <q-icon name="lock" color="teal-7" />
            </template>
            <template v-slot:append>
              <q-icon
                :name="showPassword ? 'visibility_off' : 'visibility'"
                class="cursor-pointer"
                @click="showPassword = !showPassword"
              />
            </template>
          </q-input>

          <div class="row justify-between items-center q-mt-none wrap">
            <q-checkbox v-model="rememberMe" label="Remember me" color="teal" />
            <q-btn label="Forgot Password?" flat color="teal" size="sm" class="q-px-none q-mt-xs q-mt-sm-none" />
          </div>

          <div class="q-mt-lg">
            <q-btn label="Sign In" type="submit" color="teal-7" unelevated size="lg" class="full-width rounded-borders" :loading="isLoading" />
          </div>
        </q-form>

        <q-form v-else @submit.prevent="handleRegister" class="q-gutter-y-md">
          <q-input
            v-model="name"
            label="Full Name"
            type="text"
            outlined
            lazy-rules
            :rules="[(val) => !!val || 'Name is required']"
          >
            <template v-slot:prepend>
              <q-icon name="person" color="teal-7" />
            </template>
          </q-input>

          <q-input
            v-model="email"
            label="Email Address"
            type="email"
            outlined
            lazy-rules
            :rules="[(val) => !!val || 'Email is required']"
          >
            <template v-slot:prepend>
              <q-icon name="email" color="teal-7" />
            </template>
          </q-input>

          <q-input
            v-model="password"
            label="Password"
            :type="showPassword ? 'text' : 'password'"
            outlined
            lazy-rules
            :rules="[(val) => !!val || 'Password is required']"
          >
            <template v-slot:prepend>
              <q-icon name="lock" color="teal-7" />
            </template>
            <template v-slot:append>
              <q-icon
                :name="showPassword ? 'visibility_off' : 'visibility'"
                class="cursor-pointer"
                @click="showPassword = !showPassword"
              />
            </template>
          </q-input>

          <q-input
            v-model="confirmPassword"
            label="Confirm Password"
            :type="showPassword ? 'text' : 'password'"
            outlined
            lazy-rules
            :rules="[
              (val) => !!val || 'Please confirm your password',
              (val) => val === password || 'Passwords do not match',
            ]"
          >
            <template v-slot:prepend>
              <q-icon name="check_circle" color="teal-7" />
            </template>
          </q-input>

          <div class="q-mt-lg">
            <q-btn label="Create Account" type="submit" color="teal-7" unelevated size="lg" class="full-width rounded-borders" :loading="isLoading" />
          </div>
        </q-form>
      </q-card-section>

      <q-card-actions align="center" class="q-pb-lg q-pt-none text-body2 flex-column flex-center">
        <div class="text-grey-8 text-center">
          {{ isLogin ? "Don't have an account?" : "Already have an account?" }}
          <br class="mobile-only" />
          <q-btn
            :label="isLogin ? 'Sign Up' : 'Log In'"
            flat
            color="orange"
            class="q-ml-xs text-weight-bold"
            @click="toggleForm"
          />
        </div>
      </q-card-actions>
    </q-card>
  </q-page>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { useQuasar } from "quasar";

const $q = useQuasar();

const isLogin = ref(true);
const isLoading = ref(false);
const showPassword = ref(false);
const rememberMe = ref(false);

const name = ref("");
const email = ref("");
const password = ref("");
const confirmPassword = ref("");

onMounted(() => {
  const savedEmail = localStorage.getItem("saas_remembered_email");
  if (savedEmail) {
    email.value = savedEmail;
    rememberMe.value = true;
  }
});

const toggleForm = () => {
  isLogin.value = !isLogin.value;
  password.value = "";
  confirmPassword.value = "";
  showPassword.value = false;
};

const handleLogin = async () => {
  isLoading.value = true;
  try {
    await new Promise((resolve, reject) => {
      setTimeout(() => {
        if (email.value === "test@test.com") reject(new Error("Invalid credentials"));
        resolve({ token: "fake-jwt-token-12345", user: { name: "Admin" } });
      }, 1500);
    });

    const token = "fake-jwt-token-12345";
    localStorage.setItem("saas_auth_token", token);

    if (rememberMe.value) {
      localStorage.setItem("saas_remembered_email", email.value);
    } else {
      localStorage.removeItem("saas_remembered_email");
    }

    $q.notify({ type: "positive", message: "Successfully logged in!", position: "top" });
  } catch (error) {
    $q.notify({ type: "negative", message: error.message || "Failed to login.", position: "top" });
  } finally {
    isLoading.value = false;
  }
};

const handleRegister = async () => {
  isLoading.value = true;
  try {
    await new Promise((resolve) => setTimeout(resolve, 1500));
    $q.notify({ type: "positive", message: "Account created successfully! Please log in.", position: "top" });
    toggleForm();
  } catch (error) {
    $q.notify({ type: "negative", message: "Registration failed.", position: "top" });
  } finally {
    isLoading.value = false;
  }
};
</script>

<style scoped>
.rounded-borders {
  border-radius: 12px;
}
.flex-column {
  display: flex;
  flex-direction: column;
}
.mobile-only {
  display: none;
}
@media (max-width: 599px) {
  .mobile-only {
    display: block;
  }
}
</style>