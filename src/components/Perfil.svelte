<script>
    

    export let user = [];
    
</script>

<main>
    {#if user.id}
    <h1>{user.first_name}</h1>
    <div class="card">
        <div class="card-header text-center">
              <img src={user.avatar} style="border-radius:50%" class="img-rounded" alt="">
        </div>
        <div class="card-body text-center">
              <h2>{user.first_name} {user.last_name}</h2>
              <h3>{user.email}</h3>
        </div>
    </div>
    {/if}
</main>