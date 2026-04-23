<!DOCTYPE html>
<html>
<head>
<title>For You ❤️</title>

<style>
body {
    margin: 0;
    text-align: center;
    font-family: Arial;
    background: linear-gradient(to right, #ff758c, #ff7eb3);
    color: white;
}

#box {
    margin-top: 100px;
}

button {
    padding: 12px 20px;
    font-size: 18px;
    border: none;
    border-radius: 10px;
    margin: 10px;
}

#img {
    width: 250px;
    display: none;
    border-radius: 15px;
}

.fade {
    animation: fade 1s;
}

@keyframes fade {
    from {opacity: 0;}
    to {opacity: 1;}
}
</style>
</head>

<body>

<div id="box">
    <h2 id="text">I have something to tell you... 💌</h2>
    <button onclick="start()">Start</button>
</div>

<img id="img">

<script>

let messages = [
"Hey... 😔",
"I know I made a mistake...",
"I'm really really sorry...",
"You are my favourite person ❤️",
"Please don't be angry...",
"I am really sorry ratchasi 😞",
"seriously ennaku notification varala app laiyum message varala",
"unna ignore pannanum na naa yen call ah three ring la atten panna poren eruma",
"sorry eruma maadu",
];

let i = 0;

function start(){
    document.querySelector("button").style.display="none";
    next();
}

function next(){
    if(i < messages.length){
        typeText(messages[i]);
        i++;
    } else {
        showFinal();
    }
}

function typeText(msg){
    let text = document.getElementById("text");
    text.innerHTML = "";
    let j = 0;

    let typing = setInterval(()=>{
        text.innerHTML += msg[j];
        j++;
        if(j == msg.length){
            clearInterval(typing);
            setTimeout(next,1500);
        }
    },50);
}

function showFinal(){
    let text = document.getElementById("text");
    text.innerHTML = "Will you forgive me? 🥺";

    let img = document.getElementById("img");
    img.src = "yourphoto.jpg"; // 👉 change this
    img.style.display = "block";
    img.classList.add("fade");

    document.getElementById("box").innerHTML += `
    <br>
    <button onclick="yes()">YES ❤️</button>
    <button onclick="no()">NO 😜</button>
    `;
}

function yes(){
    document.body.innerHTML = "<h1>Thank you 😭❤️</h1><p>You made me the happiest person 💖</p>";
}

function no(){
    alert("Please sorry Kit kat vangi tharen 🥺💔 ");
}

</script>

</body>
</html>
