<template>
  <div class="modalWrap">
      <div class="modalContainer">
          <div>
              <slot name="header"></slot>
          </div>
          <div>
              <slot name="footer"></slot>
          </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
_.modalWrap{width:100%; height:100%; background:rgba(0,0,0,0.4);
position: fixed;z-index: 10;}
.modalContainer{
    background: skyblue;
    position: fixed;
    width:300px;padding:20px 30px;
    left:50%;top:50%;transform: translate(-50%,-50%);
}
</style>