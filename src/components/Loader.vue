<template>
  <div class="loader">
    <div class="loader-circle"></div>
  </div>
</template>



<style>
.loader {
  background: white;
  position: absolute;
  z-index: 10;
  left: 0;
  top: 0;

  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.loader-circle {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  border: 20px solid lightgray;
  border-top: 20px solid dodgerblue;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

</style>
