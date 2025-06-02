# MiniEntregaJS

Función para validar un formulario.


Mini entrega Trabjo JavaScript
En este repositorio explico un ejemplo de que código de JavaScript puede ser necesario para mi proyecto y justifico la elección.

En nuestro proyecto, nos serviría una función para analizar respuestas sobre síntomas médicos. Si detecta signos de alarma, recomienda ir a la guardia. Si no, sugiere cuidados en casa. 


¿Cómo funciona la función?
- Primero, agarramos el formulario del documento HTML que tiene el nombre "formulario" y lo guardo en una variable:

const form = document.forms['formulario-guardia'];

- Luego, creamos una variable que al principio está en "falso", o sea, asumimos que la persona no necesita ir a la guardia. Salvo que detectemos lo contrario.

let irAGuardia = false;

-Luego creamos un bucle que revisa 7 campos del formulario, llamados "alarma1" hasta "alarma7". Si alguno de esos campos tiene el valor "si", eso significa que la persona tiene un signo de alarma médica. En ese caso, cambiamos irAGuardia a true, y usamos break para salir del bucle, porque ya con un solo síntoma es suficiente.

for (let i = 1; i <= 7; i++) {
  if (form[`alarma${i}`].value === "si") {
    irAGuardia = true;
    break;
  }
}


- Luego, buscamos un elemento en la página con el id "resultado", que es donde vamos a mostrar el mensaje final.

const resultadoDiv = document.getElementById("resultado");

- Ahora mostramos el resultado.

if (irAGuardia) {
  resultadoDiv.innerHTML = "...";
  resultadoDiv.style.backgroundColor = "...";
} else {
  resultadoDiv.innerHTML = "...";
  resultadoDiv.style.backgroundColor = "...";
}


- Si se detectó algún síntoma de alarma (irAGuardia == true): Se muestra un mensaje de alerta en rojo, diciendo que la persona debe ir a la guardia.
Si no hay signos de alarma: Se muestra un mensaje más tranquilo, con un fondo celeste, diciendo que puede cuidarse en casa por ahora.

