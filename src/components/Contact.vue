<template>
  <div class="contact">
    <slot></slot>
    <div>
      <div class="label">Name</div>
      {{ contact.name }}
    </div>
    <div>
      <div class="label">Lastname</div>
      {{ contact.lastname }}
    </div>  

    <div class="btn" @click="removeContact()">DELETE</div>

  </div>
</template>

<script>
export default {
  name: 'Contact',
  props: {
    contact : Object
  },
  methods : {

    removeContact : function() {

      this.$emit('delete', this.contact.id);
    }
  }
}
</script>
