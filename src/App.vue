<template>
  <div class="container">
    <header class="App-header my-5">
      <h1 class="font-weight-bold">VUTTR</h1>
      <h2 class="text-muted">Very Useful Tools to Remember</h2>
    </header>

    <router-view/>
  </div>
</template>

<style lang="scss">
$primary: #365df0;
$success: #0dcb7d;
$danger: #f95e5a;

@import "node_modules/bootstrap/scss/bootstrap";
@import url("https://fonts.googleapis.com/css?family=Source+Sans+Pro:200,400,600&display=swap");
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.8.2/css/all.min.css");

* {
  font-family: "Source Sans Pro", sans-serif;
  font-weight: normal;
}
*:focus {
  outline: none !important;
  box-shadow: none !important;
}

.container {
  max-width: 720px !important;
}

.modal-wrapper {
  width: 560px !important;
  max-height: 85vh;
  margin: 72px auto !important;
  overflow: auto;
}
.modal-container {
  position: fixed !important;
  z-index: 10 !important;
  top: 0 !important;
  left: 0 !important;
  width: 100% !important;
  height: 100% !important;
  background-color: rgba(23, 12, 58, 0.9) !important;
  transition: opacity 0.3s ease !important;
}

label {
  color: #170c3a !important;
}

.form-control {
  color: #170c3a !important;
  background-color: #f5f4f6 !important;
  border: solid 1px #ebeaed !important;
}
.form-control:focus {
  background-color: #ebeaed !important;
  border: solid 1px #dedce1 !important;
}

.card {
  border: solid 1px #ebeaed;
}

.btn {
  border: none !important;
}

.btn-primary {
  color: #ffffff !important;
  background-color: #365df0 !important;
}
.btn-primary:hover {
  color: #ffffff !important;
  background-color: #2f55cc !important;
}
.btn-primary:active {
  color: #ffffff !important;
  background-color: #244aa8 !important;
}
.btn-primary:disabled {
  color: #e1e7fd !important;
  background-color: #b9c6fa !important;
}

.btn-outline-primary {
  color: #365df0 !important;
  background-color: #e1e7fd !important;
}
.btn-outline-primary:hover {
  color: #365df0 !important;
  background-color: #cad6fc !important;
}
.btn-outline-primary:active {
  color: #365df0 !important;
  background-color: #b9c6fa !important;
}
.btn-outline-primary:disabled {
  color: #b9c6fa !important;
  background-color: #e1e7fd !important;
}

.btn-danger {
  color: #ffffff !important;
  background-color: #f95e5a !important;
}
.btn-danger:hover {
  color: #ffffff !important;
  background-color: #cc4c4c !important;
}
.btn-danger:active {
  color: #ffffff !important;
  background-color: #a53f3f !important;
}
.btn-danger:disabled {
  color: #feefee !important;
  background-color: #fcaeac !important;
}

.btn-outline-danger {
  color: #f95e5a !important;
  background-color: #feefee !important;
}
.btn-outline-danger:hover {
  color: #f95e5a !important;
  background-color: #fcd7d6 !important;
}
.btn-outline-danger:active {
  color: #f95e5a !important;
  background-color: #fcc6c5 !important;
}
.btn-outline-danger:disabled {
  color: #fcaeac !important;
  background-color: #feefee !important;
}
</style>
