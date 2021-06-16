<script>

    import Perfil from './Perfil.svelte'
 
    var users = [];

    var user;

    getUsers();
    async function  getUsers (){
        const resp = await fetch("https://reqres.in/api/users");
        const data = await resp.json();
        users = data.data;
    }

    function setId(p0){
       user = p0;
    }
    

</script>

<main>
    
   
    <div class="row">
        <div class="col-md-6">
            <h1 >Users</h1>
            {   #each users as user }
                <div class="list-group">
                    <div on:click={setId(user)} class="list-group-item list-group-item-action align-items-center d-flex justify-content-between">
                        <img src={user.avatar} class="img-fluid " style="border-radius: 50%;" alt="">
                        <div>
                            <h3>{user.first_name} {user.last_name } </h3>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
        <div class="col-md-4">
            <Perfil user={user} ></Perfil>
        </div>
    </div>
</main>