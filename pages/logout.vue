<template>
  <div class="container loader3">loading..</div>
</template>

<script setup>
const supa = useSupabaseClient()

async function keluar() {
  const { error } = await supa.auth.signOut()
  if (!error) navigateTo('/')
}


onMounted(() => {
  keluar()
})
</script>

<style scoped>
.loader3:before,
.loader3:after,
.loader3 {
  border-radius: 50%;
  width: 2.5em;
  height: 2.5em;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
  -webkit-animation: load7 1.8s infinite ease-in-out;
  animation: load7 1.8s infinite ease-in-out;
}

.loader3 {
  font-size: 10px;
  margin: 80px auto;
  position: relative;
  text-indent: -9999em;
  -webkit-transform: translateZ(0);
  -ms-transform: translateZ(0);
  transform: translateZ(0);
  -webkit-animation-delay: -0.16s;
  animation-delay: -0.16s;
}

.loader3:before {
  left: -3.5em;
  -webkit-animation-delay: -0.32s;
  animation-delay: -0.32s;
}

.loader3:after {
  left: 3.5em;
}

.loader3:before,
.loader3:after {
  content: '';
  position: absolute;
  top: 0;
}

@-webkit-keyframes load7 {

  0%,
  80%,
  100% {
    box-shadow: 0 2.5em 0 -1.3em #0008fa;
  }

  40% {
    box-shadow: 0 2.5em 0 0 #23268e;
  }
}

@keyframes load7 {

  0%,
  80%,
  100% {
    box-shadow: 0 2.5em 0 -1.3em #0008fa;
  }

  40% {
    box-shadow: 0 2.5em 0 0 #2c2f91;
  }
}
</style>
