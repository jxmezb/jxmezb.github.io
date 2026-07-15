---
layout: page
title: Games
permalink: /games/
---


<div class="games-window">


    <div class="title-bar">

        🎮 Games Explorer

    </div>



    <div class="menu-bar">

        File &nbsp;&nbsp; Edit &nbsp;&nbsp; View &nbsp;&nbsp; Help

    </div>




    <div class="games-body">


        <div class="game-icon" onclick="startSnakeGame()">

            <div class="icon-image">
                🐍
            </div>

            <div>
                Snake.exe
            </div>

        </div>



        <div class="game-icon">

            <div class="icon-image">
                🏓
            </div>

            <div>
                Pong.exe
            </div>

            <small>
                Coming Soon
            </small>

        </div>




        <div class="game-icon">

            <div class="icon-image">
                💣
            </div>

            <div>
                Minesweeper.exe
            </div>

            <small>
                Coming Soon
            </small>

        </div>


    </div>



</div>





<div id="game-container"></div>






<style>


body {

background:#008080 !important;

}





.games-window {


width:500px;

background:#c0c0c0;

border:2px solid black;

box-shadow:

inset -2px -2px white,

inset 2px 2px #808080;


font-family:

Tahoma,
Arial,
sans-serif;


}





.title-bar {


background:#000080;

color:white;

font-weight:bold;

padding:4px;

display:flex;

align-items:center;


}




.menu-bar {


background:#c0c0c0;

color:black;

padding:5px;

border-bottom:2px solid #808080;

font-size:14px;


}




.games-body {


background:white;

border:

2px inset #808080;


margin:8px;

padding:15px;


display:flex;

gap:30px;

min-height:150px;


}





.game-icon {


width:90px;

text-align:center;

cursor:pointer;

padding:8px;

font-size:13px;


}





.icon-image {


font-size:32px;

margin-bottom:5px;


}





.game-icon:hover {


background:#000080;

color:white;


}





.game-icon small {


display:block;

font-size:10px;

color:#555;


}




.game-icon:hover small {


color:white;


}




.game-window {


margin-top:20px;

width:500px;

background:#c0c0c0;

border:2px solid black;


}




.game-header {


background:#000080;

color:white;

padding:4px;


}




canvas {


background:black;

display:block;

margin:15px auto;


}



button {


font-family:Tahoma;

background:#c0c0c0;

border:2px solid;

border-color:white black black white;

padding:5px 15px;


}



</style>
