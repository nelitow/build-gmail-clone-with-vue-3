<template>
  <div class="email-display">
    <h2 class="mb-0">
      {{ email.subject }}
    </h2>
    <div>
      <small> {{ email.from }} on {{ format(new Date(email.sentAt), "dd MMM y") }}</small>
    </div>
    <p v-html="marked(email.body)"></p>
  </div>
</template>
<script>
import { format } from "date-fns";
import marked from 'marked'
export default {
  setup(props) {
    return {
      format,
      marked,
    };
  },
  props: {
    email: {
      type: Object,
      required: true,
    },
  },
};
</script>