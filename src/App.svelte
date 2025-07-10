<script>
  let name = "Avneek Kaur"; // Change this to your name
  let favoriteNumber = 23; // Change this to your favorite number
  let bio = "I am a computer science major looking into doing web development!";
  let hobbies = ["Traveling", "Baking", "Drawing"]; // List some hobbies

  import ImageCard from "./lib/ImageCard.svelte";
  
  let cardData = [
    {
      image:
        "https://i.imgur.com/NsfRd7R.jpeg",
      title: "Traveling",
      description:
        "I mainly enjoy traveling to see the beautiful view at night in the plane!",
    },
    {
      image: "https://i.imgur.com/Bc7dodq.jpeg",
      title: "Baking",
      description: "Baking allows me to test taste new recipes for family gatherings!",
    },
    {
      image: "https://i.imgur.com/5HGNyUF.jpeg",
      title: "Drawing",
      description:
        "I enjoy drawing because there's no right or wrong way to draw something!",
    },
  ];
</script>

<style>
  h1 {
    color: #4f3765;
    font-family: Arial, sans-serif;
  }
  .container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
  }
  .hobbies {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
  }
  .hobby {
    background-color: #ac78dd;
    color: white;
    padding: 10px 15px;
    border-radius: 5px;
  }
</style>

<div class="container">
  <h1>About Me</h1>
  <p>Hello, my name is <strong>{name}</strong>!</p>
  <p>My favorite number is <strong>{favoriteNumber}</strong>.</p>
  <p>{bio}</p>

  <h2>My Hobbies</h2>
  <div class="hobbies">
    {#each hobbies as hobby}
      <div class="hobby">{hobby}</div>
    {/each}
  </div>

  <h2>Some of My Favorite Things</h2>
  <div class="card-container">
    {#each cardData as { image, title, description }}
      <ImageCard {image} {title} {description} />
    {/each}
  </div>
</div>
