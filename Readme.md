# Streaming twitter con kafka simple con producer y consumer

Demo de streaming de tuits usando la api de Twitter y enviando los tuis a kafka.

&nbsp;

## Requerimientos

* Docker

```
https://www.docker.com/get-started
```

* Acceso a la API de Twitter

Para generar la app developer y obtener las key

```url
https://developer.twitter.com/en/docs/twitter-api/getting-started/getting-access-to-the-twitter-api
```


* Git

```url
https://git-scm.com
```

* Instalar los requerimientos de python:
```
pip install -r requirements.txt
```

&nbsp;

## Ejecución

1. Clonar el repositorio

```
git clone https://github.com/ezeparziale/streaming-twitter-kafka-simple.git .
```

2. Ejecutar el archivo docker-compose.yaml

```
docker-compose -f "docker-compose.yaml" up -d
```

3. Configurar los parametros
   
* Configurar el archivo *config.py* seteando la variable **TOPIC_NAME** con el valor del topico que queremos crear
```
TOPIC_NAME = 'twitter'
```

* Configurar los token de la api de twitter
```
API_KEY = 'INGRESAR_LA_API_KEY'
API_SECRET_KEY = 'INGRESAR_LA_API_SECRET_KEY'
ACCESS_TOKEN = 'INGRESAR_EL_ACCESS_TOKEN'
ACCESS_TOKEN_SECRET = 'INGRESAR_EL_ACCESS_TOKEN_SECRET'
```

* Configurar las variables de busqueda:
```
TRACKS = ['#argentina','argentina','boca','river','ronaldo','messi','psg','barcelona','manchesterd']
LOCATION = [-126.2,-56.0,22.3,58.9]
LANGUAGES = ['en','es']
```

&nbsp;

4. Ejecutar el archivo **new_topic.py** para crear el topico en kafka.
   
5. Ejecutar el archivo **producer.py** para correr el producer de kafka.
   
Este archivo va a conectarse a twitter y leer los tuits con los parametros establecidos y los va a disponibilizar en el topico.

6. Ejecutar el archivo **consumer.py** para ir leyendo los datos del topico.

Este archivo va a estar conectandose al topico, leer los datos e imprimirlos por pantalla.