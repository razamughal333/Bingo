
<!DOCTYPE html>
<html>
    <head>
        <title>Bingo</title>
        <meta charset="UTF-8">
        <script>
var imageclickes = [];
var count = 0;
function chargementPage() {
  document.getElementById('encore').style.visibility = 'hidden';
  let i = 1;
  while (i < 10) {
      const numb = Math.floor(Math.random() * 3 + 1);
      switch (numb) {
        case 1: {
          document.getElementById('frame' + i).value = numb;       
          break;
        }
        case 2: {
          document.getElementById('frame' + i).value = numb;
          break;
        }
        case 3: {
          document.getElementById('frame' + i).value = numb;
          break;
        }
      }
      i++;
    }
  }
function affImg(e) {
    

  if (count < 3) {  
    document.getElementById(e.target.id).removeAttribute("onclick");
    imageclickes[count] = e.target.value;
    document.getElementById(e.target.id).src = 'type' + e.target.value + '.png';
  }
  
  if (count == 3) {
      if (imageclickes[0] == imageclickes[1] && imageclickes[0] == imageclickes[2]) {
        alert('Congrats ! You won !');
      } else {
        alert("Try again ... Maybe you'be more lucky !?");
      }
      document.getElementById('encore').style.visibility = 'visible';
    } 
    count++;
}
        </script>
        <style>
            div{float:center;width:700px;}
            h1{font-family:"Brush Script MT";color:#aaa}
            body{font-family:"Calibri";background-position:center;background-attachment:scroll;background-size: cover;}
            button{border-radius:3px;background-color:rgba(255,255,255,0.5)}
        </style>
    </head>
    <body onload="chargementPage()" background="background.jpg">
    <center>
        <h1>Bingo !</h1>

        <br />
        <div>
            <img id="frame1" onclick="affImg(event)" src="unknown.png"/>
            <img id="frame2" onclick="affImg(event)" src="unknown.png"/>
            <img id="frame3" onclick="affImg(event)" src="unknown.png"/>
        </div>
        <br />
        <div>
            <img id="frame4" onclick="affImg(event)" src="unknown.png"/>
            <img id="frame5" onclick="affImg(event)" src="unknown.png"/>
            <img id="frame6" onclick="affImg(event)" src="unknown.png"/>
        </div>
        <br />
        <div>
            <img id="frame7" onclick="affImg(event)" src="unknown.png"/>
            <img id="frame8" onclick="affImg(event)" src="unknown.png"/>
            <img id="frame9" onclick="affImg(event)" src="unknown.png"/>
        </div>

        <br />
        <button id="encore" onclick="location.reload()" >Again ?</button>
    </center>
</body>
</html>
