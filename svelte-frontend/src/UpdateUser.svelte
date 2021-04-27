<script>
  import axios from "axios";

  const api = "http://localhost:3000/users";

  let userID;
  let userData = { firstName: "", lastName: "" };

  function updateUser() {
    if (!userID) return;

    axios.patch(`${api}/${userID}`, userData).then((response) => {
      location.reload();
    });
  }
</script>

<div class="card">
  <h2>Update User</h2>
  <label for="id">ID</label>
  <input bind:value={userID} type="number" />
  <label for="firstName">First Name</label>
  <input bind:value={userData.firstName} type="text" />
  <label for="lastName">Last Name</label>
  <input bind:value={userData.lastName} type="text" />
  <button on:click={updateUser}>Submit</button>
</div>

<style>
  h2 {
    text-align: center;
  }
</style>
