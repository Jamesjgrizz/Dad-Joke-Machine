# Dad-Joke-Machine
This project shows how to call an API in JavaScript. I'll also add the HTML and CSS files to show how I built and styled the page.

```JS
const jokebtn = document.getElementById("jokebtn")
const joke = document.getElementById("joke")

jokebtn.addEventListener('click', generateJoke)

generateJoke ()

async function generateJoke () {
    const config = {
        headers: {
            'Accept': 'application/json' 
        }
    }
    const response = await fetch('https://icanhazdadjoke.com', config) 

    const data = await response.json()

    joke.innerHTML = data.joke
}
```
HTML
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css" integrity="sha512-Evv84Mr4kqVGRNSgIGL/F/aIDqQb7xQ2vcrdIwxfjThSH8CSR7PBEakCr51Ck+w+/U6swU2Im1vVX0SVk9ABhg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <link rel="stylesheet" href="joke.css">
    <title>DadJokeMachine</title>
</head>
<body>
    <div class="container">
        <h3 class="h3">Joke Machine</h3>
        <div class="joke" id="joke">Joke Goes Here</div>
        <button id="jokebtn" class="btn">Generate joke</button>
    </div>

    <script src="joke.js"></script>
</body>
</html>
```
CSS
```
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&family=Titan+One&display=swap');

* {
    box-sizing: border-box;
}

body {
    background-image: url("./dadJokes.jpg");
    background-size: cover;
    font-family: "Roboto", sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    overflow: hidden;
    padding: 20px ;
}

.container {
    background-color: rgb(243, 240, 237);
    border-radius: 10px;
    text-align: center;
    padding: 40px;
    max-width: 100%;
    width: 500%;
    box-shadow: 0 10px 20px rgb(0, 0,0,1), 0 6px 6px;
    opacity: 0.8;


   
}

.joke {
    margin: 50px auto;
    line-height: 40px;
    letter-spacing: 1px;
    font-size: 30px;
    max-width: 600px;
    
}

.btn {
    background-color: rgb(227, 218, 32);
    box-shadow: 0 10px 20px rgb(0, 0,0,1), 0 6px 6px;
    padding: 14px 40px;
    border: 0;
    border-radius: 10px;
    color: rgb(0, 0, 0);
    font-size: 16px;
    cursor: pointer;
}

.btn:focus {
    outline: 0;
}

.btn:active {
    transform: scale(0.98);

}



.h3 {
    margin: 0;
    letter-spacing: 2px;
}
```






