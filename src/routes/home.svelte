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

</style>

<div id="home_bg">
<div class="bg-gradient-to-t from-black">
    <h1 class="pt-60 lg:text-6xl">Book the ideal musicians for your events</h1> 
    <h2 class="my-8">Choose between 1000+ musicians to find the perfect band or professional DJ for an unforgettable event</h2> 

    <div class="presentation">
        <h3>What is LiveMusic?</h3> 
        <h4>Find your dream artist</h4>
        <p>Whatever your music taste, the band of your dreams is on LiveMusic</p> 
        <h4>Our musicians are verified professional</h4>
        <p>Each musician on the platform is carefully chosen by our experts</p> 
        <h4>Choose between 1000+ artists</h4>
        <p>An infinity of musical universes to make sure you find the perfect match</p> 
        <h4>Try us, you'll love it</h4>
        <p>With a satisfaction rate of 86 %, our clients love what we do</p>
    </div> 

    <div class="event_type">
        <h3>Kind of events we provide</h3> 
        <ul>
            <li>Private party</li>
            <li>Wedding</li>
            <li>Birthday</li>
            <li>Cocktail</li>
        </ul>
    </div> 

    <div class="music_style">
    <h3>Find the perfect style for your event:</h3> 
        <ul>
            <li>Jazz</li>
            <li>Rock</li>
            <li>Hip hop</li>
            <li>Electronic music</li>
            <li>Classical</li>
            <li>Pop</li>
        </ul>
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
                <p class="text-black">Wow. We loved the simplicity of the webiste and the rock band I booked for my husband's birthday was simply perfect!</p>
                <p class="text-black">- Susie M.</p> 
            </div>
        </div> 

        <!---<h4>Popular bands</h4>
        <p>BandName1</p>
        <p>BandName2</p>
        <p>BandName3</p> --->

        <h4>Excellent global rating</h4>
        <p>86 % of our clients recommend us, with a global rating of "excellent"</p> 

    </div>
</div> 
</div>
