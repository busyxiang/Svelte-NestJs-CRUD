<script>
  import axios from "axios";

  const createUserAPI = "http://localhost:3000/users";

  let userData = { firstName: "", lastName: "" };

  function createUser() {
    axios.post(createUserAPI, userData).then((response) => {
      location.reload();
    });
  }
</script>

<div class="card">
  <h2>Create User</h2>
  <label for="firstName">First Name</label>
  <input bind:value={userData.firstName} type="text" />
  <label for="lastName">Last Name</label>
  <input bind:value={userData.lastName} type="text" />
  <button on:click={createUser}>Submit</button>
</div>

<style>
  h2 {
    text-align: center;
  }
</style>
