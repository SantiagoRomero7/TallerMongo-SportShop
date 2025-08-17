# 🏀 SportShop Online

SportShop Online es una tienda virtual especializada en artículos deportivos.  
Permite a los usuarios registrarse, buscar y comprar productos, dejar reseñas, usar cupones y participar en promociones.  
El sistema está pensado para una aplicación web responsive.  

👨‍💻 **Desarrolladores**: Ricardo Palomino y Santiago Romero — *los mejores* 🚀

---

## 📂 Estructura del proyecto

```plaintext
TallerMongo-SportShop/
│
├── usuarios.json
├── productos.json
├── pedidos.json
├── reseñas.json
├── cupones.json
└── README.md
```
## ⚙️ Creación de la base de datos

En tu terminal de MongoDB:

```bash
use sportshop

``` 
---
## 📥 Importar colecciones

Desde la terminal de tu sistema operativo, usar **mongoimport** para cargar los datos:

```bash
mongoimport --db sportshop --collection usuarios  --file usuarios.json  --jsonArray
mongoimport --db sportshop --collection productos --file productos.json --jsonArray
mongoimport --db sportshop --collection pedidos   --file pedidos.json   --jsonArray
mongoimport --db sportshop --collection reseñas   --file reseñas.json   --jsonArray
mongoimport --db sportshop --collection cupones   --file cupones.json   --jsonArray
```

# 📊 Consultas con Expresiones Regulares en MongoDB

A continuación se listan **25 consultas prácticas** que muestran cómo aplicar **Regex** en el sistema.

---

## 👤 Usuarios

🔹 **1. Buscar usuarios cuyo nombre comienza con "Car"**
```bash
db.usuarios.find({ "nombre": { "$regex": "^Car", "$options": "i" } })
🔹 2. Buscar usuarios con correos de Gmail

bash
Copiar
Editar
db.usuarios.find({ "correo": { "$regex": "@gmail\\.com$", "$options": "i" } })
🔹 3. Buscar usuarios que viven en ciudades terminadas en "otá"

bash
Copiar
Editar
db.usuarios.find({ "ciudad": { "$regex": "otá$", "$options": "i" } })
🔹 4. Filtrar usuarios cuyo teléfono empieza en 310

bash
Copiar
Editar
db.usuarios.find({ "telefono": { "$regex": "^310" } })
🔹 5. Buscar usuarios cuyo rol contenga la palabra "admin"

bash
Copiar
Editar
db.usuarios.find({ "rol": { "$regex": "admin", "$options": "i" } })
🛒 Productos
🔹 6. Buscar productos cuyo nombre comience con "Pro"

bash
Copiar
Editar
db.productos.find({ "nombre": { "$regex": "^Pro", "$options": "i" } })
🔹 7. Filtrar productos con descripciones que mencionen "resistente"

bash
Copiar
Editar
db.productos.find({ "descripcion": { "$regex": "resistente", "$options": "i" } })
🔹 8. Buscar productos de marcas que terminen en "Sport"

bash
Copiar
Editar
db.productos.find({ "marca": { "$regex": "Sport$", "$options": "i" } })
🔹 9. Filtrar productos cuyo nombre tenga la palabra "ball"

bash
Copiar
Editar
db.productos.find({ "nombre": { "$regex": "ball", "$options": "i" } })
🔹 10. Buscar productos con tallas que empiecen por "M"

bash
Copiar
Editar
db.productos.find({ "talla": { "$regex": "^M", "$options": "i" } })
📦 Pedidos
🔹 11. Buscar pedidos con ID que empiece en "ORD"

bash
Copiar
Editar
db.pedidos.find({ "id_pedido": { "$regex": "^ORD" } })
🔹 12. Filtrar pedidos de clientes cuyo nombre tenga "Ana"

bash
Copiar
Editar
db.pedidos.find({ "cliente": { "$regex": "Ana", "$options": "i" } })
🔹 13. Buscar pedidos con estado "pendiente" (sin importar mayúsculas)

bash
Copiar
Editar
db.pedidos.find({ "estado": { "$regex": "pendiente", "$options": "i" } })
🔹 14. Buscar pedidos cuya dirección termine en "Colombia"

bash
Copiar
Editar
db.pedidos.find({ "direccion": { "$regex": "Colombia$", "$options": "i" } })
🔹 15. Filtrar pedidos que tengan referencia de producto que empiece con "PRD"

bash
Copiar
Editar
db.pedidos.find({ "productos": { "$elemMatch": { "id_producto": { "$regex": "^PRD" } } } })
⭐ Reseñas
🔹 16. Buscar reseñas que contengan la palabra "excelente"

bash
Copiar
Editar
db.reseñas.find({ "comentario": { "$regex": "excelente", "$options": "i" } })
🔹 17. Filtrar reseñas donde el usuario empiece por "Juan"

bash
Copiar
Editar
db.reseñas.find({ "usuario": { "$regex": "^Juan", "$options": "i" } })
🔹 18. Buscar reseñas que terminen con un signo de admiración "!"

bash
Copiar
Editar
db.reseñas.find({ "comentario": { "$regex": "!$" } })
🔹 19. Filtrar reseñas que mencionen "entrega" en el comentario

bash
Copiar
Editar
db.reseñas.find({ "comentario": { "$regex": "entrega", "$options": "i" } })
🔹 20. Buscar reseñas de productos cuyo ID empiece por "PRD"

bash
Copiar
Editar
db.reseñas.find({ "id_producto": { "$regex": "^PRD" } })
🎟️ Cupones
🔹 21. Buscar cupones cuyo código empiece en "DESC"

bash
Copiar
Editar
db.cupones.find({ "codigo": { "$regex": "^DESC" } })
🔹 22. Filtrar cupones con códigos que terminen en "2025"

bash
Copiar
Editar
db.cupones.find({ "codigo": { "$regex": "2025$" } })
🔹 23. Buscar cupones cuya descripción contenga "envío gratis"

bash
Copiar
Editar
db.cupones.find({ "descripcion": { "$regex": "envío gratis", "$options": "i" } })
🔹 24. Buscar cupones aplicables a categorías que incluyan "ropa"

bash
Copiar
Editar
db.cupones.find({ "categorias": { "$regex": "ropa", "$options": "i" } })
🔹 25. Filtrar cupones que contengan porcentajes en la descripción ("%")

bash
Copiar
Editar
db.cupones.find({ "descripcion": { "$regex": "%" } })