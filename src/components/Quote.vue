<template>
  <div class="col-sm-6 col-md-6 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    props: ['quotes']
  }
</script>
<style>
  .panel-body {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 24px;
    color: rgb(58, 9, 104);
  }

  .quote {
    cursor: pointer;
  }

  .quote:hover {
    color: rgb(218, 203, 232)
  }
</style>