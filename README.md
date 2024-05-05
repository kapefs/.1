<!DOCTYPE html>
<html>
    <meta name="viewport" content="width=device-width, initial-scale=1">

<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">

    <style>
    @media(max-width: 992px){
    }
    @media(max-width: 768px){
    }
    
    @media(max-width: 500px){
    }
#calc {
    width: 300px;
    padding: 10px;
    border: 1px solid #000000;
    border-radius: 5px;
    text-align: center;
    color: blue;
    margin: 50px auto;


}

#calc button {
    width: 60px;
    height: 60px;
    font-size: 18px;
    margin: 5px;
    cursor: pointer;
    color: rgb(199, 41, 41);
}

#display {
    width: 80%;
    height: 40px;
    font-size: 24px;
    margin: 10px auto;
    color: coral;
    
}

#navbar ul{
display: none;
background-color: #f90;
position: absolute;
top: 100%;
}
#navbar li:hover ul { display: block; }
#navbar, #navbar ul{
margin: 0;
padding: 0;
list-style-type: none;
}
#navbar {
height: 50px;
background-color: #5f5a5a;
padding-left: 25px;
min-width: 470px;
}
#navbar li {
float: left;
position: relative;
height: 100%;
}
#navbar li a {
display: block;
padding: 15px;
width: 100px;
color: #fff;

text-align: center;
}
#navbar ul li { float: none; }
#navbar li:hover { background-color: #f90; }
#navbar ul li:hover { background-color: rgb(167, 106, 15); }
p{
    text-align: center;
    color: #fff;
    padding: 0.3px;
    
}
h2{
    text-align: center;
    color: #fff;
    padding: 15px;

}
#weights{
    background-color:#5f5a5a ;
}
body{}

    </style>    




</head>
<body>
    <ul id="navbar">
        <li><a href="#">Главная</a></li>
        <li><a href="#">Новости</a></li>
        <li><a href="#">Калькуляторы</a>
          <ul>
            <li><a href="#">Простой</a></li>
            <li><a href="#">Математический</a></li>
            <li><a href="#">Онлайн</a></li>
          </ul>
        </li>
        
      </ul>
      
    <div id="calc">
        <input type="text" id="display" disabled>
        <br>
        <button onclick="addToDisplay('7')">7</button>
        <button onclick="addToDisplay('8')">8</button>
        <button onclick="addToDisplay('9')">9</button>
        <button onclick="addToDisplay('+')">+</button>
        <br>
        <button onclick="addToDisplay('4')">4</button>
        <button onclick="addToDisplay('5')">5</button>
        <button onclick="addToDisplay('6')">6</button>
        <button onclick="addToDisplay('-')">-</button>
        <br>
        <button onclick="addToDisplay('1')">1</button>
        <button onclick="addToDisplay('2')">2</button>
        <button onclick="addToDisplay('3')">3</button>
        <button onclick="addToDisplay('*')">*</button>
        <br>
        <button onclick="addToDisplay('0')">0</button>
        <button onclick="clearDisplay()">C</button>
        <button onclick="calculateResult()">=</button>
        <button onclick="addToDisplay('/')">/</button>
    </div>
    <div id="weights">
    <h2>Конвентеры веса:</h2>
<p>Граммы в Киллограммы: </p>

<p>
  <label>Киллограммы</label>
  <input id="inputKilograms" type="number" placeholder="Киллограммы" oninput="weightConverter(this.value)" onchange="weightConverter(this.value)">
</p>
<p>Граммы: <span id="outputGrams"></span></p>


<p>Граммы в Фунты:</p>

<p>
  <label>Граммы:ㅤㅤ</label>
  <input id="inputGrams" type="number" placeholder="Граммы" oninput="weightConverter2(this.value)" onchange="weightConverter2(this.value)">
</p>
<p>Фунты: <span id="outputPounds"></span></p>

>
<p>Граммы в унции:</p>

<p>
  <label>Граммы:ㅤㅤ</label>
  <input id="inputGrams" type="number" placeholder="Граммы" oninput="weightConverter3(this.value)" onchange="weightConverter3(this.value)">
</p>
<p>Унции: <span id="outputOunces"></span></p>
</div>
    <script>
  function addToDisplay(value) {
            document.getElementById('display').value += value;
        }
        function clearDisplay() {
            document.getElementById('display').value = '';
        }
        function calculateResult() {
            try {
                document.getElementById('display').value = eval(document.getElementById('display').value);
            } catch (error) {
                document.getElementById('display').value = 'Error';
            }
        }
        function weightConverter(valNum) {
  document.getElementById("outputGrams").innerHTML=valNum*1000;
}
function weightConverter2(valNum) {
  document.getElementById("outputPounds").innerHTML=valNum*0.0022046;
}
function weightConverter3(valNum) {
  document.getElementById("outputOunces").innerHTML=valNum*0.035274;
}
    </script>
</body>
</html>