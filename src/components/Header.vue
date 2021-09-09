<template>
  <header class="">
    <div class="my-container row justify-content-between align-items-center">
      <div class="col-10">
        <img src="../assets/img/logo.png" alt="" class="" />
      </div>
      <div class="col-2">
          <!--TODO: inserire i campi -->
        <select class="form-select" aria-label="Default select example">
          <option selected>Open this select menu</option>
          <option value="1">One</option>
          <option value="2">Two</option>
          <option value="3">Three</option>
        </select>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss">
@import "../assets/scss/vars.scss";
header {
  height: 90px;
  width: 100%;
  background-color: $secondary-color;
  box-shadow:  0px  0px 10px rgba($green-spotify,0.4);

  position: fixed;
  top: 0;
  left: 0;

  .row {
    height: 100%;
    width: 100%;
  }
  img {
    max-width: 5%;
  }
}
</style>