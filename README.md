#Mi primer Autómata Finito

###Por: Juana del Carmen Banda Mosqueda.
###Materia: Compiladores.
###Maestra: Merari Perez Valencia.

Ahora, expliquemos cada parte:

##1. **Declaración del tipo de documento y encabezado HTML:**
![image](https://github.com/JuanaBanda/automata_Finito/assets/122316068/fd594d04-d358-4164-9c75-eb73f37c1820)

    
     
    `<!DOCTYPE html> <html lang="es"> <head>     <meta charset="UTF-8">     <meta name="viewport" content="width=device-width, initial-scale=1.0">     <title>Automata Finito en JavaScript con Gráfico</title>     <script src="https://d3js.org/d3.v5.min.js"></script> </head>`
    
    - `<!DOCTYPE html>`: Declara el tipo de documento como HTML5.
    - `<html lang="es">`: Indica que el idioma del documento es español.
    - `<head>`: Contiene metadatos y referencias externas.
    - `<meta charset="UTF-8">`: Especifica el conjunto de caracteres UTF-8.
    - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Configura la visualización en dispositivos móviles.
    - `<title>`: Define el título de la página.
    - `<script src="https://d3js.org/d3.v5.min.js"></script>`: Incluye la biblioteca D3.js desde su CDN.
##2. **Cuerpo del HTML y código JavaScript:**
    ![image](https://github.com/JuanaBanda/automata_Finito/assets/122316068/0ffba490-e62d-4656-9b06-346cf489ba22)

    
    `<body>     <script>         // Contenido del script     </script> </body> </html>`
    
##3. **Definición del autómata (JavaScript):**
![image](https://github.com/JuanaBanda/automata_Finito/assets/122316068/be734352-047e-46ad-92ce-5694f6eef671)

     
    `class AutomataFinito {     constructor() {         this.estadoActual = 'q0';         this.estadosAceptacion = ['q1'];     }      procesarCadena(cadena) {         for (const caracter of cadena) {             this.transicion(caracter);         }          return this.estadosAceptacion.includes(this.estadoActual);     }      transicion(caracter) {         switch (this.estadoActual) {             // ... (lógica de transición)         }     } }`
    
    - Se define una clase `AutomataFinito` que representa un autómata con métodos para procesar cadenas y realizar transiciones.
##4. **Creación del autómata y procesamiento de una cadena:**
    ![image](https://github.com/JuanaBanda/automata_Finito/assets/122316068/6889150a-fb59-4fbb-b124-749627111852)

   
    `const automata = new AutomataFinito(); const cadenaEjemplo = 'abababab'; const resultado = automata.procesarCadena(cadenaEjemplo);`
    
    - Se instancia un objeto `automata` de la clase `AutomataFinito`.
    - Se define una cadena de ejemplo y se procesa utilizando el autómata.
##5. **Creación del gráfico con D3.js:**
![image](https://github.com/JuanaBanda/automata_Finito/assets/122316068/35cadc5a-402f-43aa-81c3-3567e388be52)
   
    ``const svg = d3.select('body').append('svg').attr('width', 300).attr('height', 100);  svg.append('text')     .attr('x', 10)     .attr('y', 30)     .text(`Cadena "${cadenaEjemplo}" es ${resultado ? 'válida' : 'inválida'}`);  svg.append('circle').attr('cx', 30).attr('cy', 70).attr('r', 10).style('fill', 'lightblue'); svg.append('circle').attr('cx', 100).attr('cy', 70).attr('r', 10).style('fill', 'lightgreen'); svg.append('text').attr('x', 30).attr('y', 70).text('q0'); svg.append('text').attr('x', 100).attr('y', 70).text('q1');``
    
    - Se utiliza D3.js para seleccionar el cuerpo del documento (`'body'`), agregar un elemento SVG y establecer sus dimensiones.
    - Se añade un elemento de texto para mostrar el resultado del procesamiento de la cadena.
    - Se añaden círculos y texto para representar los estados del autómata.
    

![image](https://github.com/JuanaBanda/automata_Finito/assets/122316068/b98e4d0f-e4cf-417a-8ce3-427e94306e7a)

