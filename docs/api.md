# API REST

## Introducción

La API REST de EcoRide permite la comunicación entre la aplicación móvil y el servidor. Utiliza el formato JSON para enviar y recibir información.

## URL base

La dirección base de la API es:

`https://ecoride/api`

Todas las rutas se construyen a partir de esta dirección.

## GET https://ecoride/api/stations

**Finalidad:** Obtener la lista de estaciones disponibles.

**Respuesta JSON:**

```json
{
    "estaciones": [
        {
            "id": 1,
            "nombre": "Estación Centro",
            "bicicletas_disponibles": 8,
            "activa": true
        },
        {
            "id": 2,
            "nombre": "Estación Norte",
            "bicicletas_disponibles": 5,
            "activa": true
        }
    ]
}
```

## GET https://ecoride/api/bikes

**Finalidad:** Consultar las bicicletas disponibles.

**Respuesta JSON:**

```json
{
    "bicicletas": [
        {
            "id": 101,
            "estacion_id": 1,
            "disponible": true
        },
        {
            "id": 102,
            "estacion_id": 1,
            "disponible": true
        }
    ]
}
```

## POST https://ecoride/api/reservations

**Finalidad:** Crear una reserva de bicicleta.

**Cuerpo de la petición JSON:**

```json
{
    "usuario_id": 12,
    "bicicleta_id": 101
}
```

**Respuesta JSON:**

```json
{
    "id": 50,
    "usuario_id": 12,
    "bicicleta_id": 101,
    "estado": "confirmada",
    "mensaje": "Reserva realizada correctamente"
}
```

## GET https://ecoride/api/users/{id}

**Finalidad:** Consultar la información de un usuario mediante su identificador.

**Respuesta JSON:**

```json
{
    "id": 12,
    "nombre": "Carlos",
    "email": "carlos@gmail.com",
    "activo": true
}
```
