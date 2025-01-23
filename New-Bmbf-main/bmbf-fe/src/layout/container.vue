<template>
  <div  class="d-flex justify-content-center align-items-center flex-column" >
    <div class="startBg">
      <button class="btn btn-last  position-fixed start-0 top-50 a">
        <i class="fa-solid fa-arrow-left"></i>
      </button>
      <button class="btn btn-next  position-fixed end-0 top-50 a">
        <i class="fa-solid fa-arrow-right"></i>
      </button>
      <slot name="start-content"></slot>
    </div>
  </div>
  <button type="button" class=" btn-outline-secondary d-flex justify-content-center align-items-center">
    <i class="fa-solid fa-x"></i>
    <span> Anmeldung Abbrechen </span>
  </button>

</template>

<script>
export default {};
</script>

<style scoped>




.btn-last {
  border-radius: 0 50% 50% 0;
  background-color: #a19c98;
  width: 350px;
  height: 264.21px;
}
.btn-next {
  border-radius: 50% 0 0 50%;
  background-color: #4be381;
  width: 350px;
  height: 264.21px;
}


.a i {
  font-size: 127px;
}

.btn-outline-secondary i {
  font-size: 60px;
  color: black;
}
.btn-outline-secondary
{
  background-color: transparent;
  gap: 40px;
  margin-top: 47px;
  margin-left: 230px;
  width: 617px;
  height: 90px;
  border-radius: 20px;
  border: 4px solid #000;
}

.btn-outline-secondary span
{
  color: #000;
  font-size: 45px;
  font-style: normal;
  font-weight: 420;
  line-height: 26.784px; /* 59.52% */
}

</style>