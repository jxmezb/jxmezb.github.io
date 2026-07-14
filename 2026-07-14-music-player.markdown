---
layout: post
title:  "Music Player"
date:   2026-07-14
categories: jekyll update
---
















<div class="music-player">

    <h3>My Music Player</h3>

    <p id="song-name">No song selected</p>

    <audio id="audio-player"></audio>

    <button onclick="previousSong()">⏮ Previous</button>
    <button onclick="playSong()">▶ Play</button>
    <button onclick="pauseSong()">⏸ Pause</button>
    <button onclick="nextSong()">⏭ Next</button>

    <br><br>

    <input 
        type="range" 
        id="volume" 
        min="0" 
        max="1" 
        step="0.01" 
        value="1"
    >

</div>


<script>

const songs = [
    {
        name: "-",
        file: "/assets/music/-.mp3"
    },
    {
        name: "AHCU_-_1st_Privacy_Tool_for_Windows_7.3.2.1crk",
        file: "/assets/music/AHCU_-_1st_Privacy_Tool_for_Windows_7.3.2.1crk.mp3"
    },
    {
        name: "BReWErS_-_Turok_2008_8trn",
        file: "/assets/music/BReWErS_-_Turok_2008_8trn.mp3"
    }
];


let currentSong = 0;

const audio = document.getElementById("audio-player");
const songName = document.getElementById("song-name");
const volume = document.getElementById("volume");


function loadSong() {

    audio.src = songs[currentSong].file;
    songName.textContent = songs[currentSong].name;

}


function playSong() {

    audio.play();

}


function pauseSong() {

    audio.pause();

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


volume.addEventListener("input", function(){

    audio.volume = volume.value;

});


loadSong();

</script>
