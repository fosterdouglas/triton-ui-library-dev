<docs>

<h3>Timed</h3>
<p>Used when a particular fuction has a timeout limit.</p>

```js
<template>
  <div>

    <b-button
      @click="showAlert"
      variant="outline-primaryfade"
      class="btnNavigation btnStandard"
      onclick="this.blur();"
      >
      Show Timed Alert
    </b-button>

    <b-alert
      :show="dismissCountDown"
      fade
      variant="secondary"
      class="customAlert"
      @dismissed="dismissCountDown=0"
      @dismiss-count-down="countDownChanged"
    >
      <p class="mb-2">{{ TimedTitle }}{{ dismissCountDown }}</p>
      <b-progress
        variant="secondary"
        :max="dismissSecs"
        :value="dismissCountDown"
        height="4px"
      ></b-progress>
    </b-alert>



  </div>
</template>

<script>
  export default {
    data() {
      return {
        dismissSecs: 30,
        dismissCountDown: 0,
        TimedTitle: 'This alert will complete in '
      }
    },
    methods: {
      countDownChanged(dismissCountDown) {
        this.dismissCountDown = dismissCountDown
      },
      showAlert() {
        this.dismissCountDown = this.dismissSecs
      }
    }
  }
</script>
```

</docs>
