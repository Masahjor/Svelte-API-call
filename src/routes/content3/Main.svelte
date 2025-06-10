<!-- ===== Script ===== -->
<script lang="ts">
    let city = "Copenhagen";
    let weather: any = null;
    let apiKey = "9855952b01e98dac8ef73b53521f0019"; // Replace with your OpenWeatherMap API key

    // Weather for Grenå
    let grenaaWeather: any = null;
    let odenseWeather: any = null;
    let copenhagenWeather: any = null;

    // Fetch Grenå weather automatically on component mount
    import { onMount } from 'svelte';
    onMount(async () => {
        const res = await fetch(
            `https://api.openweathermap.org/data/2.5/weather?q=Grenaa,DK&appid=${apiKey}&units=metric`
        );
        grenaaWeather = await res.json();
        console.log('Grenå Weather API response:', grenaaWeather);
    });

    onMount(async () => {
        const res = await fetch(
            `https://api.openweathermap.org/data/2.5/weather?q=Odense,DK&appid=${apiKey}&units=metric`
        );
        odenseWeather = await res.json();
        console.log('Odense Weather API response:', odenseWeather);
    });

    onMount(async () => {
        const res = await fetch(
            `https://api.openweathermap.org/data/2.5/weather?q=Copenhagen,DK&appid=${apiKey}&units=metric`
        );
        copenhagenWeather = await res.json();
        console.log('Copenhagen Weather API response:', copenhagenWeather);
    });

    const getWeather = async () => {
        const res = await fetch(
            `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`
        );
        weather = await res.json();
        console.log('Weather API response:', weather);
    }
</script>

<!-- ===== HTML ===== -->
<div class="grid-container">
    
    <div class="grid-item" style="grid-column: span 3;">
        <h2>Weather API - Cities of interest</h2>
    </div>

    <!-- GRENAA -->
    <div class="grid-item">
        {#if grenaaWeather && grenaaWeather.main && grenaaWeather.wind}
            <div class="grid-item">
                <h3>Weather in Grenå</h3>
                <p>Temperature: {grenaaWeather.main.temp}°C</p>
                <p>
                    Condition: {grenaaWeather.weather[0].description}
                    <img 
                        src={`https://openweathermap.org/img/wn/${grenaaWeather.weather[0].icon}@2x.png`} 
                        alt={grenaaWeather.weather[0].description} 
                        width="48"
                        height="48"
                    />
                </p>
                <p>Wind speed: {grenaaWeather.wind.speed} m/s</p>
                <p>Air humidity: {grenaaWeather.main.humidity}%</p>
            </div>
        {/if}
    </div>

    <!-- ODENSE -->
    <div class="grid-item">
        {#if odenseWeather && odenseWeather.main && odenseWeather.wind}
            <div class="grid-item">
                <h3>Weather in Odense</h3>
                <p>Temperature: {odenseWeather.main.temp}°C</p>
                <p>
                    Condition: {odenseWeather.weather[0].description}
                    <img 
                        src={`https://openweathermap.org/img/wn/${odenseWeather.weather[0].icon}@2x.png`} 
                        alt={odenseWeather.weather[0].description} 
                        width="48"
                        height="48"
                    />
                </p>
                <p>Wind speed: {odenseWeather.wind.speed} m/s</p>
                <p>Air humidity: {odenseWeather.main.humidity}%</p>
            </div>
        {/if}
    </div>

    <!-- COPENHAGEN -->
    <div class="grid-item">
        {#if copenhagenWeather && copenhagenWeather.main && copenhagenWeather.wind}
            <div class="grid-item">
                <h3>Weather in Copenhagen</h3>
                <p>Temperature: {copenhagenWeather.main.temp}°C</p>
                <p>
                    Condition: {copenhagenWeather.weather[0].description}
                    <img 
                        src={`https://openweathermap.org/img/wn/${copenhagenWeather.weather[0].icon}@2x.png`}
                        alt={copenhagenWeather.weather[0].description}
                        width="48"
                        height="48"
                    />
                </p>
                <p>Wind speed: {copenhagenWeather.wind.speed} m/s</p>
                <p>Air humidity: {copenhagenWeather.main.humidity}%</p>
            </div>
        {/if}
    </div>



    <div class="grid-item" style="grid-column: span 3;">
        <h2>Weather API call</h2>
        <input bind:value={city} placeholder="Enter city name" />
        <button on:click={getWeather}>Get Weather</button>
        {#if weather && weather.main}
            <div>
                <h3>Weather in {weather.name}</h3>
                <p>Temperature: {weather.main.temp}°C</p>
                <p>
                    Condition: {weather.weather[0].description}
                    <img 
                        src={`https://openweathermap.org/img/wn/${weather.weather[0].icon}@2x.png`} 
                        alt={weather.weather[0].description} 
                        width="48"
                        height="48"
                    />
                </p>
                <p>Wind speed: {weather.wind.speed} m/s</p>
                <p>Air humidity: {weather.main.humidity}%</p>
            </div>
        {/if}
    </div>

    <div class="grid-item item-invisible" style="grid-column: span 3;">
      <p>Secret text :)</p>
    </div>
</div>