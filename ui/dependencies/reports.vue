<template>
  <div>
    <b-table striped hover :items="items"></b-table>
  </div>
</template>

<script>
    const myRequest = new Request('https://jsonplaceholder.typicode.com/users');
    const myURL = myRequest.url; // http://localhost/api
    const myMethod = myRequest.method; // GET
    const myCred = myRequest.credentials; // omit
    module.exports = {
       mounted () {
      fetch(myRequest)
      .then(response => response.json())
      .then(response => {
        this.items = response;
        console.log(response);
        // ...
      }).catch(error => {
        console.error(error);
      });
    },
    data() {
      return {
        items: null
      }
    }
  }
</script>