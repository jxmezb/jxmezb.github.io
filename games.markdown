---
layout: page
title: Games
permalink: /games/
---


<audio id="game-launch-sound" preload="auto">
    <source src="/assets/sounds/microsoft-windows-98-startup-soundmp3_160k.mp3" type="audio/mp3">
</audio>


<div class="games-window">


    <div class="title-bar">

        🎮 Games Explorer

    </div>



    <div class="menu-bar">

        File &nbsp;&nbsp; Edit &nbsp;&nbsp; View &nbsp;&nbsp; Help

    </div>




    <div class="games-body">


        <div class="game-icon" ondblclick="launchGame('snake')">

            <div class="icon-image">
                🐍
            </div>

            <div>
                Snake.exe
            </div>

        </div>



        <div class="game-icon" ondblclick="launchGame('pong')">

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




        <div class="game-icon" ondblclick="launchGame('minesweeper')">

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


    
/* Windows 98 Icon Selection Animation */

.game-icon {

    transition: transform 0.1s;

}


.game-icon:active {

    transform: scale(0.9);

}


.game-icon.selected {

    background:#000080;

    color:white;

}


    
</style>






<script>

/* ==========================
   Windows 98 Games Explorer
   ========================== */


// Single-click selects an icon
document.querySelectorAll(".game-icon").forEach(function(icon){

    icon.addEventListener("click", function(){

        document.querySelectorAll(".game-icon").forEach(function(i){

            i.classList.remove("selected");

        });

        this.classList.add("selected");

    });

});




// Double-click launches the selected game
document.querySelectorAll(".game-icon").forEach(function(icon){

    icon.addEventListener("dblclick", function(){

        let game = this.getAttribute("data-game");

        launchGame(game);

    });

});





function launchGame(game){

    // Play launch sound
    const sound = document.getElementById("game-launch-sound");

    if(sound){

        sound.currentTime = 0;

        sound.play().catch(function(){});

    }


    switch(game){

        case "snake":

            startSnakeGame();

            break;


        case "pong":

            alert("Pong.exe is coming soon!");

            break;


        case "minesweeper":

            alert("Minesweeper.exe is coming soon!");

            break;


        default:

            console.log("Unknown game.");

    }

}





/* ==========================
   Snake Launcher
   ========================== */

function startSnakeGame(){

    document.getElementById("game-container").innerHTML = `

        <div class="game-window">

            <div class="game-header">

                🐍 Snake.exe

            </div>

            <p style="padding:15px;">

                Snake will go here next.

            </p>

        </div>

    `;

}

</script>
