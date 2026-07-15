---
layout: page
title: 
permalink: /music-player/
---

<div class="rain-container"></div>

<div class="win98-player">

    <div class="title-bar">
        <span>🎵 Music Player</span>

        <div class="window-buttons">
            <button>_</button>
            <button>□</button>
            <button>X</button>
        </div>
    </div>


    <div class="player-body">

        <div class="display">
            <span id="song-title">No song selected</span>
        </div>


        <audio id="audio-player"></audio>


        <div class="controls">
            <button onclick="previousSong()">|◀◀</button>
            <button onclick="playSong()">▶</button>
            <button onclick="pauseSong()">❚❚</button>
            <button onclick="nextSong()">▶▶|</button>
        </div>


        <div class="volume">

            Volume:

            <input 
                id="volume"
                type="range"
                min="0"
                max="1"
                step="0.01"
                value="1"
            >

        </div>


        <div class="playlist">

            <div class="playlist-header">
                Playlist
            </div>

            <ul id="playlist-list"></ul>

        </div>

    </div>

</div>



<style>

/* =========================
   Rain Effect
   ========================= */


.rain-container {

    position: fixed;

    top:0;
    left:0;

    width:100%;
    height:100%;

    overflow:hidden;

    pointer-events:none;

    z-index:0;

}


.rain-drop {

    position:absolute;

    top:-50px;

    width:2px;

    height:25px;

    background:#00ffff;

    opacity:.35;

    animation:rain linear infinite;

}


@keyframes rain {

    from {

        transform:translateY(-50px);

    }

    to {

        transform:translateY(110vh);

    }

}



/* =========================
   Windows 98 Player
   ========================= */


.win98-player {

    position:relative;

    z-index:2;

    width:360px;

    background:#c0c0c0;

    border:2px solid black;

    font-family:"MS Sans Serif",Tahoma,sans-serif;

    box-shadow:
    inset -2px -2px white,
    inset 2px 2px #808080;

}



.title-bar {

    background:navy;

    color:white;

    padding:4px;

    display:flex;

    justify-content:space-between;

    font-weight:bold;

}



.window-buttons button {

    width:22px;

    height:18px;

    padding:0;

    font-weight:bold;

}



.player-body {

    padding:10px;

}



.display {

    background:black;

    color:lime;

    padding:8px;

    font-family:monospace;

    margin-bottom:10px;

}



.controls {

    display:flex;

    gap:5px;

    margin-bottom:10px;

}



button {

    background:#c0c0c0;

    border:2px solid;

    border-color:white black black white;

    padding:5px 10px;

    font-family:inherit;

}



button:active {

    border-color:black white white black;

}



.playlist {

    border:2px solid;

    border-color:black white white black;

    background:white;

}



.playlist-header {

    background:#000080;

    color:white;

    padding:3px;

}



#playlist-list {

    list-style:none;

    margin:0;

    padding:5px;

    height:120px;

    overflow-y:auto;

}



#playlist-list li {

    cursor:pointer;

    padding:3px;

}



#playlist-list li:hover {

    background:navy;

    color:white;

}



</style>




<script>


/* =========================
   Generate Rain
   ========================= */


const rain = document.querySelector(".rain-container");


for(let i = 0; i < 100; i++) {

    let drop = document.createElement("div");

    drop.className = "rain-drop";

    drop.style.left = Math.random() * 100 + "vw";

    drop.style.animationDuration =
        (0.5 + Math.random() * 1.5) + "s";

    drop.style.animationDelay =
        Math.random() * 5 + "s";


    rain.appendChild(drop);

}




/* =========================
   Music Player
   ========================= */


const songs = [

{
name:"AHCU - 1st Privacy Tool for Windows",
file:"/assets/music/AHCU_-_1st_Privacy_Tool_for_Windows_7.3.2.1crk.mp3"
},

{
name:"-",
file:"/assets/music/-.mp3"
},
    
{
name:"BReWErS - Turok 2008",
file:"/assets/music/BReWErS_-_Turok_2008_8trn.mp3"
},

{
name:"SnD - MagicTweak 3.10",
file:"/assets/music/SnD_-_MagicTweak3.10kg.mp3"
},

{
name:"big aka - Feel The Bass",
file:"/assets/music/big_aka_feel_the_bass.mp3"
},

{
name:"tPORt - Multikeygen for Godlike Developers",
file:"/assets/music/tPORt_-_Multikeygen_for_Godlike_Developers.mp3"
}

];


let currentSong = 0;


const player = document.getElementById("audio-player");

const title = document.getElementById("song-title");

const playlist = document.getElementById("playlist-list");

const volume = document.getElementById("volume");



songs.forEach((song,index)=>{


    let item=document.createElement("li");

    item.textContent=song.name;


    item.onclick=function(){

        currentSong=index;

        loadSong();

        playSong();

    };


    playlist.appendChild(item);


});



function loadSong(){

    player.src=songs[currentSong].file;

    title.textContent=songs[currentSong].name;

}



function playSong(){

    player.play();

}



function pauseSong(){

    player.pause();

}



function nextSong(){

    currentSong++;

    if(currentSong >= songs.length){

        currentSong=0;

    }


    loadSong();

    playSong();

}



function previousSong(){

    currentSong--;

    if(currentSong < 0){

        currentSong=songs.length-1;

    }


    loadSong();

    playSong();

}



volume.addEventListener("input",()=>{

    player.volume=volume.value;

});



loadSong();


</script>
