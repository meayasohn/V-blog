

<script>
import { initializeApp } from "firebase/app";
import firebaseConfig from "../../firebaseConfig";
import {
  getAuth,
  connectAuthEmulator,
  signInWithPopup,
  GoogleAuthProvider,
} from "firebase/auth";

console.log("auth start ------------", firebaseConfig);
initializeApp(firebaseConfig);

const auth = getAuth();
connectAuthEmulator(auth, "http://localhost:9099");
auth.useDeviceLanguage();

const provider = new GoogleAuthProvider(); //google login

// signInWithPopup(auth, provider)
//   .then((result) => {
//     // This gives you a Google Access Token. You can use it to access the Google API.
//     const credential = GoogleAuthProvider.credentialFromResult(result);
//     const token = credential.accessToken;
//     // The signed-in user info.
//     const user = result.user;
//     // ...
//   })
//   .catch((error) => {
//     // Handle Errors here.
//     const errorCode = error.code;
//     const errorMessage = error.message;
//     // The email of the user's account used.
//     const email = error.email;
//     // The AuthCredential type that was used.
//     const credential = GoogleAuthProvider.credentialFromError(error);
//     // ...
//   });

export default {};
</script>

<style>
</style>

<template>
  <q-btn @click="signInWithPopup(auth, provider)" round color="info">
    <q-avatar icon="mdi-login" size="24"> </q-avatar>
  </q-btn>
</template>