## Project 1
### BMI Calculator

```Html 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bmi Calculator</title>
</head>
<body>
    <div class="conatiner">
        <form >
        <p><label for="">Height in CM:</label><input id="Height" type="text"></p>
        <p><label for="">Weight in KG:</label><input id="Weight"  type="text"></p>
        <div id="result">Result :</div>
        <button class="Calculate">Calculate</button>

    </form>
    </div>
    <script>
        
        const form = document.querySelector('form');
        const submit = document.querySelector('.Calculate');
        
        form.addEventListener('submit',(e)=>{
            e.preventDefault()
            const Heights = parseInt(document.querySelector('#Height').value);
            const Weights = parseInt(document.querySelector('#Weight').value);
            const Results = document.querySelector('#result')


            if(Heights === '' || Heights < 0 || isNaN(Heights)  ){
    Results.innerHTML = `Invaild Response ${Heights}`
            }else if(Weights === '' || Weights < 0 || isNaN(Weights)  ){
    Results.innerHTML = `Invaild Response ${Weights}`} else{
        const BMI = (Weights / ((Heights / 100) ** 2)).toFixed(2);

        // Results.innerHTML = `<span>BMI: ${BMI}</span>`;
        if (BMI < 18.6) {
    Results.innerHTML = `<p>Underweight</p>`;
} else if (BMI >= 18.6 && BMI <= 24.9) {
    Results.innerHTML = `<p>Normal weight</p>`;
} else if (BMI > 24.9) {
    Results.innerHTML = `<p>Overweight and BMI IS ${BMI}</p>`;
}


    }

        });
        //(weight/((height*height)/10000)) 18.6 24.9
    </script>
</body>
</html>
```

### Color Changer

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Color Changer</title>
</head>
<style>
    .container{
        display: flex;
        flex-direction: column;
        justify-content: center;
    }



    button{
        width: 70px;
        margin: 0 auto;
        padding: 30px;
        margin-top: 10px;
    }
    #green{
        background-color: green;
    }
    #black{
        background-color: black;

    }
    #orange{
        background-color: orange;
    }
    #white{
        background-color: white;
    }
</style>
<body>
    <div class="container">

        <button id="green"  ></button> 
        <button   id="black"  ></button>
        <button   id="white"     >

        </button>
        <button   id="orange"    > </button>

        <h1  style="color: black;">--You can change color of background according to the button color--</h1>
    </div>
    <script>
        
        const allButtons = document.querySelectorAll('button');
        const body = document.querySelector('body')
        allButtons.forEach((ele)=>{
console.log(ele);
ele.addEventListener('click',(e)=>{
if (e.target.id === 'green' || e.target.id === 'black' || e.target.id === 'orange' || e.target.id === 'white' ) {
    body.style.backgroundColor = e.target.id;
    if(e.target.id === 'white'){
        body.querySelector('h1').style.filter = "none"
    }else{
    const header = document.querySelector('h1');
header.style.filter = "invert(1)";
    }

}




})

        })
    </script>
</body>

</html>
```
