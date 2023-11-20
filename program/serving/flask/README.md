# Sirviendo el modelo usando Flask

Una aplicación Flask que sirve a un modelo TensorFlow de clasificación multiclase para determinar la especie de un pingüino.


Para ejecutar la aplicación, comience creando un entorno virtual e instalando el archivo `requirements.txt`:

```bash
$ python -m venv .venv
$ source .venv/bin/activate
$ pip install -r requirements.txt
```

El siguiente comando ejecutará el servidor Flask en el puerto `localhost` `4242`:

```bash
$ export FLASK_ENV=development && flask run --host=0.0.0.0 --port=4242
```

Ejecute el siguiente comando para probar el servidor prediciendo la especie de pingüino:

```bash
$ curl --location --request POST 'http://localhost:4242/predict' \
--header 'Content-Type: text/plain' \
--data-raw '0.6569590202313976, -1.0813829646495108, 1.2097102831892812, 0.9226343641317372, 1.0, 0.0, 0.0'
```

Debería recibir la siguiente respuesta JSON:

```json
{
    "confidence": 0.8113499283790588,
    "prediction": 2
}
```
