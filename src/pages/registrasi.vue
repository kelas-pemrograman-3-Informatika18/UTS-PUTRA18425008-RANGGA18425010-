<template>
  <q-page >
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="Your Username *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="Your Password"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
        filled
        type="NIK"
        v-model="NIK"
        label="Your NIK"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
        filled
        type="Age"
        v-model="Age"
        label="Your Age"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />
      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
 </q-page>
</template>

<script>
export default {
  data () {
    return {
      username: null,
      password: null,
      NIK: null,
      Age: null
    }
  },
  methods: {
    onSubmit () {
      console.log('Ini fungsi Sumbit')
    },
    onReset () {
      this.username = null
      this.password = null
      this.NIK = null
      this.Age = null
    }
  }
}
</script>
