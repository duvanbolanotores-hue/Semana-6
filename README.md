# Semana-6
Pregunta 1:
Respuesta: B. Un formato de intercambio de datos usado entre aplicaciones.

Pregunta 2:
Respuesta: B. Leer datos enviados en formato JSON en una petición.

Pregunta 3:
Respuesta: B. req.body

Pregunta 4:
Respuesta: C. { "nombre": "Juan" }
Al enviar una petición POST a la ruta /registro con el siguiente JSON:

{
  "nombre": "Maria",
  "mensaje": "Hola comunidad"
}

El servidor recibe los datos mediante req.body y devuelve la siguiente respuesta:

{
  "estado": "Datos recibidos",
  "nombre": "Maria",
  "mensaje": "Hola comunidad"
}

Esto confirma que la información fue recibida y procesada correctamente.Es importante que las plataformas tecnológicas puedan recibir información de forma estructurada porque facilita el procesamiento de los datos. Cuando los ciudadanos envían reportes organizados, las entidades pueden identificar problemas más rápidamente. Además, se reduce la posibilidad de errores al interpretar la información. El uso de formatos como JSON permite intercambiar datos entre diferentes sistemas de manera eficiente. También ayuda a mantener registros claros y ordenados. Gracias a esto se pueden generar estadísticas y tomar mejores decisiones. Las plataformas tecnológicas mejoran la comunicación entre ciudadanos y organizaciones. Esto contribuye a una atención más rápida de las necesidades de la comunidad. Finalmente, permite ofrecer servicios más eficientes y de mejor calidad.const express = require('express');
const app = express();

app.use(express.json());

app.post('/registro', (req, res) => {

  const nombre = req.body.nombre;
  const mensaje = req.body.mensaje;

  res.json({
    estado: "Datos recibidos",
    nombre: nombre,
    mensaje: mensaje
  });

});

app.post('/incidencia', (req, res) => {

  const tipo = req.body.tipo;
  const descripcion = req.body.descripcion;

  res.json({
    mensaje: "Incidencia registrada",
    tipo: tipo,
    descripcion: descripcion
  });

});

app.listen(3000, () => {
  console.log('Servidor ejecutándose en puerto 3000');
});
