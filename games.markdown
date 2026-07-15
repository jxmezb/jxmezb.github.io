---
layout: page
title: Games
permalink: /games/
---


<div class="games-window">

    <div class="title-bar">

        🎮 Games Explorer

    </div>



    <div class="games-body">


        <div class="game-icon" onclick="openGame('snake')">

            🐍
            <br>
            Snake.exe

        </div>



        <div class="game-icon" onclick="openGame('pong')">

            🏓
            <br>
            Pong.exe

        </div>



        <div class="game-icon">

            💣
            <br>
            Minesweeper.exe

        </div>



    </div>


</div>




<div id="game-area"></div>




<style>


body {

background:#008080 !important;

}



.games-window {


width:400px;

background:#c0c0c0;

border:2px solid black;

box-shadow:

inset -2px -2px white,

inset 2px 2px #808080;

font-family:

Tahoma,sans-serif;


}



.title-bar {


background:#000080;

color:white;

padding:5px;

font-weight:bold;


}



.games-body {


display:flex;

gap:30px;

padding:20px;


}



.game-icon {


text-align:center;

cursor:pointer;

font-size:35px;

}



.game-icon:hover {


background:#000080;

color:white;


}



</style>




<script>


function openGame(game){


let area=document.getElementById("game-area");



if(game==="snake"){


area.innerHTML=`

<h2>Snake.exe</h2>

<canvas id="snake" width="400" height="400"></canvas>

`;



startSnake();


}




}



</script>
