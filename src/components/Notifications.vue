<template>
    <div>
        <input type="button" value="show notification" @click="showNotification">
        {{ msg }}
    </div>
</template>
<style>

</style>
<script>
export default {
  name: 'notifications',
  data () {
    return {
      msg: 'TODOS!!!-!'
    }
  },
  methods: {
    showNotification: function () {
      console.log('prova')
      if (Notification.permission === 'granted') {
        var notification = new Notification('Hi there!')
        notification
      }
    }
  },
  created () {
    if (!('Notification' in window)) {
      alert('This browser does not support system notifications')
    }
    Notification.requestPermission().then(function (result) {
      console.log(result)
    })
  }
}

</script>
