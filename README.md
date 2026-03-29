1 - ========================= HTML =========================
<!DOCTYPE html>
<html>
<head>
    <title>Contador</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<h2>Total de cliques: <span id="contador">0</span></h2>
<button id="btn">Gostei 👍</button>

<script src="script.js"></script>
</body>
</html>

========================= CSS =========================
body {
    text-align: center;
    font-family: Arial;
}

button {
    padding: 10px;
}

========================= JS =========================
let contador = 0;

document.getElementById("btn").addEventListener("click", function() {
    contador++;
    document.getElementById("contador").textContent = contador;
});

2- ========================= HTML =========================
<input type="number" id="idade">
<button onclick="verificar()">Verificar</button>
<p id="resultado"></p>

========================= CSS =========================
#resultado {
    font-weight: bold;
}

========================= JS =========================
function verificar() {
    let idade = document.getElementById("idade").value;
    let res = document.getElementById("resultado");

    if (idade >= 18) {
        res.textContent = "Entrada permitida";
        res.style.color = "green";
    } else {
        res.textContent = "Entrada proibida";
        res.style.color = "red";
    }
}

3- ========================= HTML =========================
<input type="number" id="n1">
<select id="op">
    <option value="+">+</option>
    <option value="-">-</option>
    <option value="*">*</option>
    <option value="/">/</option>
</select>
<input type="number" id="n2">
<button onclick="calcular()">Calcular</button>

<p id="res"></p>

========================= JS =========================
function calcular() {
    let a = Number(n1.value);
    let b = Number(n2.value);
    let op = document.getElementById("op").value;
    let r;

    if (op == "+") r = a + b;
    else if (op == "-") r = a - b;
    else if (op == "*") r = a * b;
    else r = a / b;

    res.textContent = "Resultado: " + r;
}

4- ========================= HTML =========================
<input id="nota1">
<input id="nota2">
<button onclick="media()">Calcular</button>
<p id="saida"></p>

========================= JS =========================
function media() {
    let n1 = Number(nota1.value);
    let n2 = Number(nota2.value);
    let m = (n1 + n2) / 2;

    let s = document.getElementById("saida");

    if (m >= 7) {
        s.textContent = "Aprovado";
        s.style.color = "green";
    } else if (m >= 5) {
        s.textContent = "Recuperação";
        s.style.color = "orange";
    } else {
        s.textContent = "Reprovado";
        s.style.color = "red";
    }
}

5- ========================= HTML =========================
<input id="num">
<button onclick="gerar()">Gerar</button>
<ul id="tabuada"></ul>

========================= JS =========================
function gerar() {
    let n = Number(num.value);
    let lista = document.getElementById("tabuada");
    lista.innerHTML = "";

    for (let i = 1; i <= 10; i++) {
        let li = document.createElement("li");
        li.textContent = `${n} x ${i} = ${n * i}`;
        lista.appendChild(li);
    }
}

6- ========================= HTML =========================
<input id="missao">
<button onclick="add()">Adicionar</button>
<ul id="lista"></ul>

========================= JS =========================
function add() {
    let texto = missao.value;

    let li = document.createElement("li");
    li.textContent = texto;

    li.onclick = function() {
        li.style.textDecoration = "line-through";
    };

    lista.appendChild(li);
}

7- ========================= HTML =========================
<input id="nome">
<p id="erroNome"></p>

<input id="email">
<p id="erroEmail"></p>

<button onclick="validar()">Cadastrar</button>

========================= JS =========================
function validar() {
    let nome = nome.value;
    let email = email.value;

    erroNome.textContent = nome == "" ? "Nome obrigatório" : "";
    erroEmail.textContent = !email.includes("@") ? "Email inválido" : "";
}

8- ========================= JS =========================
let numero = Math.floor(Math.random() * 20) + 1;
let tentativas = 0;

function tentar() {
    let palpite = Number(document.getElementById("palpite").value);
    let msg = document.getElementById("msg");

    tentativas++;

    if (palpite > numero) msg.textContent = "Muito alto";
    else if (palpite < numero) msg.textContent = "Muito baixo";
    else msg.textContent = "Acertou! Tentativas: " + tentativas;
}

9- ========================= JS =========================
let a = 0, b = 0, c = 0;

function votar(x) {
    if (x == 1) a++;
    if (x == 2) b++;
    if (x == 3) c++;

    resultado.textContent = `A:${a} B:${b} C:${c}`;
}

10- ========================= JS =========================
function cadastrar() {
    let nome = nome.value;
    let email = email.value;
    let idade = Number(idade.value);
    let senha = senha.value;
    let conf = conf.value;

    if (!nome || !email || !idade || !senha || !conf) {
        alert("Preencha tudo");
        return;
    }

    if (idade < 18) {
        alert("Menor de idade");
        return;
    }

    if (senha.length < 8) {
        alert("Senha fraca");
        return;
    }

    if (senha != conf) {
        alert("Senhas diferentes");
        return;
    }

    alert("Cadastro realizado!");
}
