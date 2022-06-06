<script setup lang="ts">
import VueForm from '@lljj/vue-json-schema-form';

const formData = {};

const schema = {
  type: 'object',
  required: ['userName', 'age'],
  properties: {
    userName: {
      type: 'string',
      title: 'Username',
      default: 'Liu.Jun',
    },
    age: {
      type: 'number',
      title: 'Age',
    },
    bio: {
      type: 'string',
      title: 'Bio',
      minLength: 10,
      default: 'The more you know, the less you know',
    },
  },
};

const uiSchema = {
  bio: {
    'ui:options': {
      placeholder: 'Please enter your bio.',
      type: 'textarea',
      rows: 1,
    },
  },
};
</script>

<template>
  <VueForm v-model="formData" :ui-schema="uiSchema" :schema="schema"> </VueForm>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
