# LLM_Estefany
Repositorio de prueba para implemtar LLM y una aplicacion web 



# 1. Instalación
como primer paso descargamos ollama de su página oficial web. 
[ollama] (https://ollama.com/download/linux) de su página web, y ejecutamos el siguiente comando :


````bash
$ curl -fsSL https://ollama.com/install.sh | sh
````

## 2. Ejecutar el servidor

Una vez que se descargo e instalo ollama se puede iniciar y detener su ejecución para que no se ejecute en segundo plano.

Para iniciar el servidor se ejecuta el siguiente comando:

````bash
$ollama serve
````

## 3. Descargar un modelo

A continuación vamos al siguiente link para descargar los modelos [modelo](https://ollama.com/library)

Antes de iniciar hay que descargar un modelo para comenzar a interactuar como el, para este proceso se ejecucta el siguiente comando:

````bash
$ollama pull tinyllama
````

Para descargar los  modelos primero debo abrir una terminal nueva y ademas el ollama serve debe estar corriendo en la anterior consola 

Nota:
 otro comdo importante es ollama list para ver cuantos modelos descargamos

 ````bash
$ollama list
 ````

 después de todo esto podemos preguntar cosas a nuestro modelo

 ````bash
$ ollama run tinyllama why sky is blue?
````

## 4. Realizar un request a la API REST

pARa realizar una consulta utilizamos el comando curl como se muestr en el sigiente ejemplo:

````bash
$ curl -X POST http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
  "prompt": "Why is the sky blue?"
}'
````


## 5. Realizar request sin stream 

Esta es la forma en la que la api la pdemos obligar a dar una sola repsuesta y no muchas request

````bash
curl -X POST http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
  "prompt": "Why is the sky blue?",
"stream": false
}'
````