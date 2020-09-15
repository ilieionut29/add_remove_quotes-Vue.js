<template>
  <div class="number-of-quotes">
        <div class="progress">
            <div class="progress-bar bg-success" r
                ole="progressbar"  
                :style="{width: (quoteCount / maxQuotes ) * 100 + '%'}"
            >
                {{quoteCount}} / {{maxQuotes}}
            </div>
        </div>
  </div>
</template>

<script>

export default {
   props: ['quoteCount', 'maxQuotes']
}
</script>

<style>
.number-of-quotes {
    margin-top: 10px;
}
.progress-bar {
     transition: 1s;
     text-align: left;
}
</style>