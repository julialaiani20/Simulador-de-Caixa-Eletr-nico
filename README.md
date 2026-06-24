<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Simulador de Caixa Eletrônico</title>
</head>
<body id="container">
    <div id="conteudo">
        <h1 id="titulo">Caixa Eletrônico</h1>
        <form id="form">
            <input id="input" type="number" placeholder="Digite o valor que deseja sacar/depositar: ">
            <button type="submit">Sacar</button>
            
        </form>

        <div id="resultado">

        </div>
    </div>
    

    <script>
        const form = document.querySelector("#form");  //pega o formulário
        const input = document.querySelector("#input");
        const resultado = document.querySelector("#resultado");
        
       

        form.addEventListener("submit", function(event){
            event.preventDefault();
            const valor = Number(input.value);
            if(valor<=0|| isNaN(valor)){
                resultado.innerHTML = "Digite um valor válido!!";
                return;
            }
            //100
            const notas100 = Math.floor(valor/100);
            const resto = valor%100;
            //50
            const notas50 = Math.floor(resto/50);
            const resto50 = resto%50;
            //20
            const notas20 = Math.floor(resto50/20);
            const resto20 = resto50%20;
            //10
            const notas10 = Math.floor(resto20/10);
            const resto10 = resto20%10;
            //5
            const notas5 = Math.floor(resto10/5);
            const resto5 = resto10%5;
            //2
            const notas2 = Math.floor(resto5/2);
            const resto2 = resto5%2;

            resultado.innerText =
                "Notas de 100: "+ notas100+ "\n"+
                "Notas de 50: "+ notas50+ "\n"+
                "Notas de 20: "+ notas20+ "\n"+
                "Notas de 10: "+ notas10+ "\n"+
                "Notas de 5: "+ notas5+ "\n"+
                "Notas de 2: "+ notas2+ "\n"+
                "Resto: "+ resto2;
    });
</script>
</body>
</html>


*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
}

body{
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #111827, #2563eb);
}


#conteudo{
    background: white;
    width: 400px;
    padding: 35px;
    border-radius: 20px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    text-align: center;
}


#titulo{
    color: #2563eb;
    margin-bottom: 25px;
    font-size: 32px;
}


#form{
    display: flex;
    flex-direction: column;
    gap: 15px;
}


#input{
    padding: 15px;
    border-radius: 10px;
    border: 2px solid #ddd;
    font-size: 16px;
    outline: none;
}


#input:focus{
    border-color: #2563eb;
}


button{
    padding: 15px;
    border: none;
    border-radius: 10px;
    background: #2563eb;
    color: white;
    font-size: 18px;
    cursor: pointer;
    transition: 0.3s;
}


button:hover{
    background: #1d4ed8;
    transform: scale(1.03);
}


#resultado{
    margin-top: 25px;
    background: #f1f5f9;
    padding: 20px;
    border-radius: 12px;
    text-align: left;
    white-space: pre-line;
    color: #111827;
    font-size: 16px;
}
