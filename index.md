<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Relógio Virtual</title>
    <style>
      body{
    background: rgb(135, 206, 235);

}



header{
    color: whitesmoke;
    text-align: center;


}
section{
    background: white;
    border-radius: 10px;
    padding: 15px;
    width: 500px;
    margin: auto;
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.555);
    font-family: "digital-7";
    

    
}
div {
        text-align: center;
        padding: 3px;
        font-size: 30px;
}
footer{
    color: whitesmoke;
    text-align: center;
    font-style: italic;


}
  
  
  </style>
</head>
<body>
    <header>
            <h1>Horas do Dia</h1>
    </header>
    <section>
        
        <div id="msg">
            <h1 class="time" id="time">10:00:00</h1>
        </div>

        
       <div id="foto">
            
            <img id= "imagem" src="manha.jpg" alt="foto do dia">


        </div> 

    </section>  
    <footer>
        <p>&copy; Ionic inc.</p>
    </footer>  
    <script>
    var msg = window.document.getElementById('msg')
var img = window.document.getElementById('imagem')


var hours, min, sec;
var clock = function() {

    var date = new Date();

    hours = date.getHours().toString().length < 2 ? "0" + date.getHours() : date.getHours();
    min = date.getMinutes().toString().length < 2 ? "0" + date.getMinutes() : date.getMinutes();
    sec = date.getSeconds().toString().length < 2 ? "0" + date.getSeconds() : date.getSeconds();

    var time = hours + ":" + min + ":" + sec;
    document.getElementById("time").innerHTML = time;
    if(hours >= 0 && hours < 12){
        img.src = 'manha.jpg'
        document.body.style.background = '#FFDD55'
        
    }   else if (hours >= 12 && hours <= 18){

        img.src = 'tarde.jpg'
        document.body.style.background = '#E9AF87'
    }   else{
        img.src = 'noite.jpg'
        document.body.style.background = '#2C3345'
    }
 



}
setInterval(  function(){
    clock()
}, 1000);
    
    
    </script>
</body>
</html>
