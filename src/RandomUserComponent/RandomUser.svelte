<script>
    // URL endpoint for fetching data : https://randomuser.me/api/
    let ifMale = null;
    let name = 'Loading...';
    let age = 0;
    let email = '';
    let location = '';
    let picture = '';
    let gender = '';
    function fetchUserData() {
        fetch('https://randomuser.me/api/')
        .then((res) => res.json())
        .then((data) => {
            let user = data.results[0];
            name = `${user.name.first} ${user.name.last}`;
            age = user.dob.age;
            email = user.email;
            location = `${user.location.city} ${user.location.state}`;
            picture = user.picture.large;
            gender = user.gender;

            ifMale = gender === 'male' ? true : false
        })
        .catch((err) => console.error(`Something went wrong !! ${err}`));
    }
    fetchUserData();

    $: userName = name;
    $: isMale = ifMale;
    $: userAge = age;
    $: userEmail = email;
    $: userLocation = location;
    $: userPicture = picture;
    $: userGender = gender;
</script>


<style>
    .user-box {
        height: 35vh;
        width: 100%;
    }
    #app-heading {
        text-align: center;
        padding-top: 2.2%;
        font-family: Verdana, Geneva, Tahoma, sans-serif;
    }
    .details {
        display: flex;
        justify-content: space-between;
        padding: 0% 20% 0 20%;
        align-items: center;
    }
    #picture>img {
        border-radius: 50%;
    }
</style>


<div style="background-color: {isMale ? 'aquamarine' : 'rebeccapurple'}; color: {isMale == false ? 'white' : ''}" class="user-box">
    <h2 id="app-heading">User Details</h2>
    <div class="details">
        <div id="user-info">
            <h2 id="user-name">Name: {userName}</h2>
            <h2 id="age">Age: {userAge}</h2>
            <h2 id="email">Email: {userEmail}</h2>
            <h2 id="location">Location: {userLocation}</h2>
            <h2 id="gender">Gender: {userGender.toUpperCase()}</h2>
        </div>
        <div id="picture">
            <img src="{userPicture}" alt="" />
        </div>
    </div>
</div>