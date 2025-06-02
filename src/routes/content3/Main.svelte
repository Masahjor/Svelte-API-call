<!-- ===== Script ===== -->
<script lang="ts">
    let city = "Copenhagen";
    let weather: any = null;
    let apiKey = "9855952b01e98dac8ef73b53521f0019"; // Replace with your OpenWeatherMap API key

    // Weather for Grenå
    let grenaaWeather: any = null;

    // Fetch Grenå weather automatically on component mount
    import { onMount } from 'svelte';
    onMount(async () => {
        const res = await fetch(
            `https://api.openweathermap.org/data/2.5/weather?q=Grenaa,DK&appid=${apiKey}&units=metric`
        );
        grenaaWeather = await res.json();
        console.log('Grenå Weather API response:', grenaaWeather);
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
</div>