# API de Productos y Carritos

Este proyecto implementa una API básica en Node.js para el manejo de productos y carritos, con persistencia de datos en archivos JSON.

## Estructura

- `products.json`: contiene los productos disponibles.
- `carts.json`: contiene los carritos y sus productos.
- `ProductsService.js`: lógica para gestionar productos.
- `CartsService.js`: lógica para gestionar carritos.
- `server.js`: definición de rutas HTTP.

## Endpoints

### Productos (`/api/products`)
- **GET /**: devuelve todos los productos.
- **GET /:pid**: devuelve producto por ID.
- **POST /**: agrega un producto. Requiere cuerpo con campos:
  - `title`, `description`, `price`, `code`, `stock`, `category`, `thumbnails` (array).
- **PUT /:pid**: actualiza campos de un producto existente.
- **DELETE /:pid**: elimina un producto por ID.

### Carritos (`/api/carts`)
- **POST /**: crea un nuevo carrito vacío.
- **GET /:cid**: devuelve el contenido del carrito.
- **POST /:cid/product/:pid**: agrega un producto al carrito o incrementa su cantidad. Requiere cuerpo opcional con `quantity`.

## Datos de prueba

### Productos sugeridos
```json
[
  {
    "title": "Producto 1",
    "description": "Descripción del producto 1",
    "price": 100,
    "code": "P001",
    "stock": 10,
    "category": "Categoría A",
    "thumbnails": []
  },
  {
    "title": "Producto 2",
    "description": "Descripción del producto 2",
    "price": 200,
    "code": "P002",
    "stock": 20,
    "category": "Categoría B",
    "thumbnails": []
  }
]
