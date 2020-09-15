<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
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
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');
    .panel-body {
        font-family: 'Dancing Script', cursive;
        font-size: 24px;
        text-align: center;
        color:black;
        margin-top: 7px;
        background-color: rgba(68, 189, 50,0.2);
        border-radius: 12px;
        border: 1px solid rgba(25, 42, 86,1.0);
        padding: 7px;
        word-wrap: break-word;
    }

    .quote {
        cursor: pointer;
    }
    .quote:hover {
        background-color:rgba(194, 54, 22,0.6)
    }
</style>