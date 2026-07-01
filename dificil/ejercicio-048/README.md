# Ejercicio 048 - MongoDB Dificil: viajes

## Dificultad

Dificil 5/5

## Tematica usada

viajes

## Contexto del problema

Una academia tecnica esta construyendo una plataforma de datos para analizar viajes. El equipo necesita guardar informacion flexible, consultarla rapido y documentar por que MongoDB es una buena opcion para este caso.

En este ejercicio trabajaras con la coleccion `inventory`. La idea no es copiar comandos sin pensar: debes decidir que forma tendran los documentos, que campos son importantes y como validar que tus consultas responden la pregunta del negocio.

## Objetivo

Preparar datos para dashboards usando MongoDB y dejando evidencia clara de los comandos ejecutados.

## Que vas a practicar

- Modelado documental.
- Insercion y consulta de documentos.
- Uso de operadores de MongoDB segun el nivel.
- Lectura de resultados y explicacion tecnica.
- Orden para entregar evidencia dentro de `resoluciones/{usuario-github}/`.

## Explicacion paso a paso

1. Lee el contexto y define que datos necesita guardar la coleccion `inventory`.
2. Crea entre 12 y 18 documentos de prueba con datos coherentes.
3. Ejecuta las consultas solicitadas y revisa si realmente responden al problema.
4. Guarda los comandos en un archivo `.mongodb.js` o `.js`.
5. Agrega un README corto dentro de tu carpeta explicando que hiciste y que aprendiste.
6. Valida que tu solucion no modifica archivos base del ejercicio.

## Instrucciones detalladas

- Crea tu carpeta personal dentro de `resoluciones/`, por ejemplo `resoluciones/ana-perez/`.
- Incluye un archivo de comandos llamado `solucion.mongodb.js`.
- Incluye evidencia textual o capturas exportadas en Markdown si el ejercicio lo pide.
- Usa nombres de campos en minuscula y con estilo consistente.
- Evita documentos con campos improvisados que no se repiten sin justificacion.
- Si usas datos inventados, que parezcan datos reales del contexto.

## Comandos de referencia

Estos comandos son una guia de arranque. Puedes adaptarlos si tu modelo lo necesita.

```javascript
db.inventory.find({ categoria: 'principal' }).explain('executionStats')
```

```javascript
db.inventory.aggregate([{ $match: { temporada: '2026' } }, { $lookup: { from: 'auditorias', localField: '_id', foreignField: 'refId', as: 'auditoria' } }, { $project: { nombre: 1, scoreFinal: { $multiply: ['$score', '$factor'] }, auditoria: 1 } }])
```

## Ejemplos de datos esperados

```javascript
{
  nombre: 'viajes-48',
  categoria: 'principal',
  puntos: 480,
  activo: true,
  metadata: {
    origen: 'campuslands',
    nivel: 'dificil'
  }
}
```

## Entregable esperado

Dentro de `resoluciones/{usuario-github}/` entrega:

- `solucion.mongodb.js` con comandos ejecutables.
- `README.md` con explicacion breve.
- Opcional: `evidencia.md` con resultados relevantes.

## Reglas

- No edites el README base del ejercicio.
- No borres `.gitkeep`.
- No subas datos privados, credenciales ni archivos pesados.
- No subas carpetas generadas por herramientas.
- Tu PR debe apuntar a `dev`, nunca a `main`.

## Consejos

- Piensa primero en la pregunta que quieres responder y luego en el documento.
- Si repites muchos datos, explica si eso es aceptable por velocidad de lectura.
- Usa `find().limit()` mientras pruebas para no saturar la salida.
- Guarda comandos en orden: creacion, insercion, consulta, actualizacion, validacion.

## Errores comunes

- Crear documentos con campos inconsistentes sin razon.
- Usar nombres como `dato1`, `info` o `x`.
- Entregar solo capturas sin comandos reproducibles.
- Resolver fuera de `resoluciones/{usuario-github}/`.
- Abrir PR hacia `main`.

## Pistas opcionales

- Preguntate que datos consultarias en una pantalla de dashboard.
- Si el ejercicio pide rendimiento, compara con y sin indice.
- Si el ejercicio pide aggregation, construye el pipeline por etapas.

## Como validar si quedo bien

- Puedes ejecutar el archivo completo sin errores en `mongosh`.
- Las consultas devuelven resultados relacionados con el contexto.
- Tu README explica el modelo y no solo repite comandos.
- Tu entrega esta en la carpeta correcta.
- El Pull Request pasa el bot de estructura.

