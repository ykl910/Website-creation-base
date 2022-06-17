<script>
import { DivideIcon } from "svelte-feather-icons";

</script>

<style>
#home_bg{
    background-image: url("/static/home_bg.jpg");
    background-size: 100%;
    background-position: top;
    background-repeat: no-repeat;
}

h3{
    margin-top: 1rem;
    margin-bottom: 1rem;
    --tw-text-opacity: 1;
    color: rgb(59 130 246 / var(--tw-text-opacity));
}

h4{
    margin-top: 16px;
}

h3{
    margin-top: 5rem;
}

img:hover { 
    opacity: 1; transform: scale(1.05) 
}

img { 
    opacity: .9; transition: all .2s;
    object-fit: cover;
    height: 300px;
    width: 400px;
    overflow: hidden;
    border-radius: 4%
}
    
</style>

<div id="home_bg">
<div class="bg-gradient-to-t from-black">
    <h1 class="pt-60 lg:text-6xl">Book the ideal musicians for your events</h1> 
    <h2 class="my-8">Choose among 1000+ musicians to find the perfect band or professional DJ for an unforgettable event</h2> 

    <div class="presentation">
        <h3>What is LiveMusic?</h3> 
        <h4>Find your dream artist</h4>
        <p>Whatever your music taste, the band of your dreams is on LiveMusic</p> 
        <h4>Our musicians are verified professional</h4>
        <p>Each musician on the platform is carefully chosen by our experts</p> 
        <h4>Choose among 1000+ artists</h4>
        <p>An infinity of musical universes to make sure you find the perfect match</p> 
        <h4>Try us, you'll love it</h4>
        <p>With a satisfaction rate of 92%, our clients love what we do</p>
    </div> 

    <div class="event_type">
        <h3>Where do our artists perform?</h3> 
        <ul>
            <li>Weddings</li>
            <li>Company events</li>
            <li>Bars</li>
            <li>Restaurants</li>
            <li>Private beaches</li>
        </ul>
        <h6></h6>
        <div class="grid lg:grid-cols-3 lg:grid-rows-1 gap-6 m-4">
            <div><img src="https://images.unsplash.com/photo-1456743625079-86a97ff8bc86?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2662&q=80" alt="livebar"></div>
            <div><img src="https://images.unsplash.com/photo-1618107095181-e3ba0f53ee59?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NHx8d2VkZGluZyUyMG11c2ljfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=800&q=60" alt = "event"></div>
            <div><img src="https://images.unsplash.com/photo-1512404871764-1cf03a297841?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2340&q=80" alt = "wedding"></div>
        </div>            
            
    </div> 

    <div class="music_style">
    <h3>What kind of style do our artists play?</h3> 
        <ul>
            <li>Jazz</li>
            <li>Rock</li>
            <li>Hip hop</li>
            <li>Electronic music</li>
            <li>Classical</li>
            <li>Pop</li>
        </ul>
        <h6></h6>
        <div class="grid lg:grid-cols-3 gap-6 m-4">
            <div><img src="https://images.unsplash.com/photo-1415201364774-f6f0bb35f28f?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2340&q=80" alt="jazz"></div>
            <div><img src="https://images.unsplash.com/photo-1498038432885-c6f3f1b912ee?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2340&q=80" alt="rock"></div>
            <div><img src="https://images.unsplash.com/photo-1521337581100-8ca9a73a5f79?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1977&q=80" alt="country"></div>
        </div> 
    </div> 

    <div class="feedback">
        <h3>What others think of us</h3> 

        <h4>Latest comments</h4>
        <div class="grid lg:grid-cols-3 gap-6 m-4">
            <div class="bg-white shadow shadow-white rounded p-4">
                <p class="text-black">Amazing website. I found the perfect jazz band for my wedding. Thank you LiveMusic for this unforgettable moment</p>
                <p class="text-black">- Leo78</p>
            </div>
            <div class="bg-white shadow shadow-white rounded p-4">
                <p class="text-black">Wow. We loved the simplicity of the webiste and the rock band I booked for my husband's birthday was simply perfect!</p>
                <p class="text-black">- Susie M.</p> 
            </div> 
            <div class="bg-white shadow shadow-white rounded p-4">
                <p class="text-black">Perfect website! I booked a jazz band for my company's event and now I'm getting a raise because my boss loved them!!</p>
                <p class="text-black">- Charlotte</p> 
            </div>
        </div> 

        <!---<h4>Popular bands</h4>
        <p>BandName1</p>
        <p>BandName2</p>
        <p>BandName3</p> --->

        <h4>Excellent global rating</h4>
        <p>92 % of our clients recommend us, with a global rating of "excellent"</p> 

    </div>
</div> 
</div>
