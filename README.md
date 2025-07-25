<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Test: ¿Cuál es tu lenguaje del amor?</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background-color: #faf4d7;
      display: flex;
      justify-content: center;
    }
    .container {
      max-width: 700px;
      text-align: center;
    }
    h1 {
      color: #f51d1d;
    }
    .question {
      margin-bottom: 25px;
      text-align: left;
    }
    button {
      padding: 12px 25px;
      background-color: #f51d1d;
      color: white;
      border: none;
      cursor: pointer;
      font-size: 1rem;
      margin-top: 20px;
    }
    #result {
      font-size: 1.2em;
      margin-top: 30px;
      font-weight: bold;
    }
  </style>
</head>
<body>

<div class="container">
<h1>¿Cuál es tu lenguaje del amor?</h1>

<form id="loveLangForm">
  <div class="question">
    <p>1. ¿Qué detalle te haría sonreír inesperadamente?</p>
    <label><input type="radio" name="q1" value="palabras"> Un mensaje espontáneo diciendo algo lindo</label><br>
    <label><input type="radio" name="q1" value="tiempo"> Que alguien cancele un plan solo para estar contigo</label><br>
    <label><input type="radio" name="q1" value="regalos"> Encontrar tu snack favorito en tu mochila</label><br>
    <label><input type="radio" name="q1" value="actos"> Que te preparen café justo como te gusta</label><br>
    <label><input type="radio" name="q1" value="contacto"> Un abrazo sin decir una palabra</label>
  </div>

  <div class="question">
    <p>2. ¿Qué te hace sentir más valorado?</p>
    <label><input type="radio" name="q2" value="actos"> Que alguien te ayude sin que lo pidas</label><br>
    <label><input type="radio" name="q2" value="tiempo"> Una tarde tranquila viendo pelis juntos</label><br>
    <label><input type="radio" name="q2" value="contacto"> Que te tomen la mano en público</label><br>
    <label><input type="radio" name="q2" value="palabras"> Que reconozcan tus logros con sinceridad</label><br>
    <label><input type="radio" name="q2" value="regalos"> Recibir algo pequeño, pero significativo</label>
  </div>

  <div class="question">
    <p>3. En un día malo, ¿qué te consuela más?</p>
    <label><input type="radio" name="q3" value="regalos"> Un regalo inesperado que te haga reír</label><br>
    <label><input type="radio" name="q3" value="palabras"> Un mensaje con palabras que te levanten el ánimo</label><br>
    <label><input type="radio" name="q3" value="tiempo"> Que alguien simplemente esté contigo</label><br>
    <label><input type="radio" name="q3" value="actos"> Que se encarguen de tus pendientes ese día</label><br>
    <label><input type="radio" name="q3" value="contacto"> Que te abracen sin necesidad de hablar</label>
  </div>

  <div class="question">
    <p>4. ¿Cuál de estas situaciones te haría sentir más especial?</p>
    <label><input type="radio" name="q4" value="tiempo"> Que alguien guarde su celular solo por ti</label><br>
    <label><input type="radio" name="q4" value="palabras"> Que te digan lo mucho que te admiran</label><br>
    <label><input type="radio" name="q4" value="regalos"> Recibir una carta o dibujo hecho a mano</label><br>
    <label><input type="radio" name="q4" value="actos"> Que alguien limpie tu espacio sin pedirlo</label><br>
    <label><input type="radio" name="q4" value="contacto"> Recibir un beso inesperado</label>
  </div>

  <div class="question">
    <p>5. ¿Qué te haría sentir más amado en tu día a día?</p>
    <label><input type="radio" name="q5" value="palabras"> Escuchar "gracias por estar aquí"</label><br>
    <label><input type="radio" name="q5" value="tiempo"> Compartir tiempo sin tener que hablar mucho</label><br>
    <label><input type="radio" name="q5" value="regalos"> Que te sorprendan con algo que querías hace tiempo</label><br>
    <label><input type="radio" name="q5" value="actos"> Que te resuelvan un problema sin que lo pidas</label><br>
    <label><input type="radio" name="q5" value="contacto"> Dormir abrazados</label>
  </div>

  <button type="button" onclick="calcularResultado()">Ver resultado</button>
</form>

<div id="result"></div>
</div>

<script>
  function calcularResultado() {
    const form = document.forms["loveLangForm"];
    const respuestas = [form.q1.value, form.q2.value, form.q3.value, form.q4.value, form.q5.value];

    const conteo = {
      palabras: 0,
      tiempo: 0,
      regalos: 0,
      actos: 0,
      contacto: 0
    };

    respuestas.forEach(r => conteo[r]++);

    let max = 0;
    let resultado = "";
    for (const tipo in conteo) {
      if (conteo[tipo] > max) {
        max = conteo[tipo];
        resultado = tipo;
      }
    }

    const mensajes = {
      palabras: "💬 Tu lenguaje del amor es: Palabras de afirmación. Te llena el alma que te digan cosas bonitas con sinceridad.",
      tiempo: "🕰️ Tu lenguaje del amor es: Tiempo de calidad. Te hace feliz compartir momentos reales sin distracciones.",
      regalos: "🎁 Tu lenguaje del amor es: Recibir regalos. Valoras los detalles que muestran que pensaron en ti.",
      actos: "🤝 Tu lenguaje del amor es: Actos de servicio. Te hace sentir amado que te cuiden con acciones concretas.",
      contacto: "🤗 Tu lenguaje del amor es: Contacto físico. Sientes conexión a través del afecto físico y la cercanía."
    };

    document.getElementById("result").innerText = mensajes[resultado];
  }
</script>

</body>
</html>
