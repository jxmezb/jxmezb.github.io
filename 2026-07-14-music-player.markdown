---
layout: page
title: Music Player
---


<p>Welcome to my music player!</p>

<div class="music-player">

    <h2>My Music Player</h2>

    <p id="song-title"></p>

    <audio id="audio-player"></audio>

    <button onclick="previousSong()">⏮ Previous</button>
    <button onclick="playSong()">▶ Play</button>
    <button onclick="pauseSong()">⏸ Pause</button>
    <button onclick="nextSong()">⏭ Next</button>

    <br><br>

    <label>
        Volume:
        <input id="volume" type="range" min="0" max="1" step="0.01" value="1">
    </label>

</div>


<script>

const songs = [
    {
        name: "AHCU - 1st Privacy Tool for Windows",
        file: "/assets/music/AHCU_-_1st_Privacy_Tool_for_Windows_7.3.2.1crk.mp3"
    },
    {
        name: "BReWErS - Turok 2008",
        file: "/assets/music/BReWErS_-_Turok_2008_8trn.mp3"
    },
    {
        name: "SnD - MagicTweak 3.10",
        file: "/assets/music/SnD_-_MagicTweak3.10kg.mp3"
    },
    {
        name: "big aka - Feel The Bass",
        file: "/assets/music/big_aka_feel_the_bass.mp3"
    },
    {
        name: "tPORt - Multikeygen for Godlike Developers",
        file: "/assets/music/tPORt_-_Multikeygen_for_Godlike_Developers.mp3"
    }
];


let currentSong = 0;

const player = document.getElementById("audio-player");
const title = document.getElementById("song-title");
const volume = document.getElementById("volume");


function loadSong() {

    player.src = songs[currentSong].file;
    title.textContent = songs[currentSong].name;

}


function playSong() {

    player.play();

}


function pauseSong() {

    player.pause();

}


function nextSong() {

    currentSong++;

    if (currentSong >= songs.length) {
        currentSong = 0;
    }

    loadSong();
    playSong();

}


function previousSong() {

    currentSong--;

    if (currentSong < 0) {
        currentSong = songs.length - 1;
    }

    loadSong();
    playSong();

}


volume.addEventListener("input", function() {

    player.volume = volume.value;

});


loadSong();

</script>
