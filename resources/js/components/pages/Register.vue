<template>
  <div>
    <h2>RegisterView</h2>
    <p>{{ errorMessage }}</p>
    <form @submit.prevent="auth.register(name, email, pass)">
      <label>
        <input type="text" v-model="name" placeholder="name" />
      </label>
      <br />
      <label>
        <input type="email" v-model="email" placeholder="email" />
      </label>
      <br />
      <label>
        <input type="password" v-model="pass" placeholder="password" />
      </label>
      <br />
      <button type="submit">登録</button>
    </form>
  </div>
</template>

<script setup>
import { useStoreAuth } from "../../store/auth";
import { storeToRefs } from "pinia";
import { ref } from "vue";

const auth = useStoreAuth();
const { errorMessage } = storeToRefs(auth);

const name = ref("");
const email = ref("");
const pass = ref("");
</script>

<style lang="scss" scoped></style>