---
layout: desktop
title: Nectar of the Blog
---


<div id="boot-screen">

    <div class="boot-box">

        <h1>
            Starting Windows 98...
        </h1>

        <div class="loading-bar">
            <div id="progress"></div>
        </div>

        <p>
            Microsoft Windows 98 Web Edition
        </p>

        <p>
            Loading Explorer.exe...
        </p>

    </div>

</div>




<div class="win98-desktop">


    <div class="desktop-icons">


        <div class="icon" ondblclick="openApp('/blog/')">

            <div class="icon-image">
                📝
            </div>

            <div>
                Blog
            </div>

        </div>



        <div class="icon" ondblclick="openApp('/music-player/')">

            <div class="icon-image">
                🎵
            </div>

            <div>
                Music Player
            </div>

        </div>



        <div class="icon" ondblclick="openApp('/about/')">

            <div class="icon-image">
                👤
            </div>

            <div>
                About Me
            </div>

        </div>



        <div class="icon" ondblclick="openApp('/projects/')">

            <div class="icon-image">
                💾
            </div>

            <div>
                Projects
            </div>

        </div>


    </div>





    <div class="computer-window">


        <div class="window-title">

            <span>
                🖥 Nectar of the Blog
            </span>


            <div>

                <button>_</button>

                <button>□</button>

                <button>X</button>

            </div>


        </div>




        <div class="window-body">


            <h2>
                Welcome to Nectar of the Blog
            </h2>


            <p>
                Welcome visitor.
            </p>


            <p>
                Double-click an icon to open an application.
            </p>


            <p>

                System:
                GitHub Pages

                <br>

                OS:
                Windows 98 Web Edition

            </p>


        </div>



    </div>





    <div class="taskbar">


        <button class="start-button">
            🪟 Start
        </button>



        <div class="clock" id="clock">
            12:00 PM
        </div>


    </div>



</div>





<style>


/* =====================
   Boot Screen
   ===================== */


#boot-screen {

    position:fixed;

    top:0;

    left:0;

    width:100%;

    height:100%;

    background:#000080;

    display:flex;

    justify-content:center;

    align-items:center;

    z-index:9999;

    color:white;

    font-family:
    "MS Sans Serif",
    Tahoma,
    sans-serif;

}



.boot-box {

    text-align:center;

}



.boot-box h1 {

    font-size:32px;

}



.loading-bar {


    width:300px;

    height:25px;

    background:black;

    border:3px inset white;

    margin:20px auto;

    overflow:hidden;


}



#progress {


    height:100%;

    width:0%;

    background:#00ff00;

    animation:loading 2.5s linear forwards;


}



@keyframes loading {


from {

width:0%;

}


to {

width:100%;

}


}





/* =====================
   Desktop
   ===================== */


body {

    background:#008080 !important;

}





.win98-desktop {


    min-height:80vh;

    position:relative;

    font-family:

    "MS Sans Serif",
    Tahoma,
    sans-serif;

    color:white;


}





.desktop-icons {


    display:flex;

    flex-direction:column;

    gap:25px;

    padding:20px;


}





.icon {


    width:90px;

    text-align:center;

    cursor:pointer;

    user-select:none;


}



.icon-image {


    font-size:42px;


}



.icon:hover {


    background:#000080;


}





/* =====================
   Main Window
   ===================== */


.computer-window {


    position:absolute;

    top:50px;

    left:220px;

    width:420px;


    background:#c0c0c0;


    color:black;


    border:2px solid black;


    box-shadow:

    inset -2px -2px white,

    inset 2px 2px #808080;


}





.window-title {


    background:#000080;


    color:white;


    padding:4px;


    display:flex;


    justify-content:space-between;


    font-weight:bold;


}





.window-title button {


    width:22px;

    height:18px;

    padding:0;


}





.window-body {


    padding:15px;


}





.window-body h2 {


    color:black !important;


}





/* =====================
   Taskbar
   ===================== */


.taskbar {


    position:fixed;


    bottom:0;


    left:0;


    width:100%;


    height:35px;


    background:#c0c0c0;


    border-top:2px solid white;


    display:flex;


    align-items:center;


    justify-content:space-between;


    padding:3px;


}





.start-button {


    font-weight:bold;


}





.clock {


    background:#c0c0c0;


    border:2px inset white;


    padding:4px 10px;


    color:black;


}


</style>





<script>


function openApp(page){

    window.location.href = page;

}





function updateClock(){


    let time = new Date();


    document.getElementById("clock").innerHTML =

    time.toLocaleTimeString([], {

        hour:"2-digit",

        minute:"2-digit"

    });


}



setInterval(updateClock,1000);


updateClock();






setTimeout(function(){


    document.getElementById("boot-screen").style.display="none";


},3000);



</script>
