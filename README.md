<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ReaktionsSpiel</title>
    <style>
        body {
            background-color: black;
            color: white;
            text-align: center;
            font-family: Arial, Helvetica, sans-serif;
            font-style: italic;
        }

        .kreis {
            background-color: transparent;
            width: 50px;
            height: 50px;         
            border-radius: 50%;
            cursor: pointer;
            position: absolute;
            
            
        }
    </style>
</head>
<body onload="movekreis()">
   <h1>Klicke den Kreis so schnell wie möglich an!</h1>
   <p id="message">Bist du Bereit?</p> 
   <div id="circle" onclick="measureTime()" class="kreis"></div>
   <script>
      let startTime;
   
    function movekreis() {
      circle.style.left =`${Math.random() * (window.innerWidth -50)}px`;
      circle.style.top =`${Math.random() * (window.innerHeight -50)}px`;
      circle.style.background = `hsl(${Math.random() * 360},100%,60%)`;
      startTime =Date.now();
    }

    function measureTime(){
        let reaktionTime = Date.now() -startTime;
        message.innerHTML =`Reaktionszeit: ${reaktionTime /1000}sekunden`;
        
        movekreis();
    }
   </script>
</body>
</html>
