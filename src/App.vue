<template>
  <div id="app">
    <Contact v-for="(contact, index) in contacts" :key="index" :contact="contact" @delete="removeContact">
      #{{index}}
    </Contact>

    <br>

    <div class="btn" @click="addNewContact()">NEW CONTACT</div>

  </div>
</template>

<script>
import Contact from './components/Contact.vue'

export default {
  name: 'App',
  components: {
    Contact
  },
  data : function() {
    return {
      contacts : [
        {
          id : 0,
          name : 'John',
          lastname : 'Doe'
        },
        {
          id : 1,
          name : 'Luke',
          lastname : 'Green'
        }        
      ]
    }
  },
  methods : {

    addNewContact : function() {

      const name = prompt('Contact name?');

      const lastname = prompt('Contact lastname?');

      const newContact = {
        id : this.contacts.length,
        name,
        lastname
      };

      this.contacts.push(newContact);
    },
    removeContact : function(contactId) {

      this.contacts.splice(contactId, 1);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
