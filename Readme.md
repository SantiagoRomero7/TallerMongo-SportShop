# 🏋️ SportShop Online

SportShop Online es una tienda virtual especializada en artículos deportivos. Permite a los usuarios registrarse, buscar y comprar productos, dejar reseñas, usar cupones y participar en promociones.  
El sistema está pensado para una aplicación web responsive que aprovecha MongoDB como motor de base de datos.

---

## 👨‍💻 Desarrolladores
- Ricardo Palomino  
- Santiago Romero  
✨ *Los mejores* ✨

---

## 📂 Estructura del Proyecto

```
taller-mongodb-sportshop/
│
├── README.md
├── usuarios.json
├── productos.json
├── pedidos.json
├── reseñas.json
├── cupones.json
```

---

## ⚙️ Instalación y Uso

1. **Clonar el repositorio**  
```bash
git clone https://github.com/SantiagoRomero7/TallerMongo-SportShop.git
cd taller-mongodb-sportshop
```

2. **Importar las colecciones a MongoDB**  
Ejemplo para importar usuarios:
```bash
mongoimport --db sportshop --collection usuarios --file usuarios.json --jsonArray
mongoimport --db sportshop --collection productos --file productos.json --jsonArray
mongoimport --db sportshop --collection pedidos --file pedidos.json --jsonArray
mongoimport --db sportshop --collection reseñas --file reseñas.json --jsonArray
mongoimport --db sportshop --collection cupones --file cupones.json --jsonArray
```

3. **Abrir MongoDB Shell o Compass** para ejecutar las consultas.

---

## 🔎 Consultas con Expresiones Regulares

A continuación se listan **25 consultas prácticas** que muestran cómo aplicar regex en el sistema.

---

## 👤 Usuarios

**1. Buscar usuarios cuyo nombre comienza con "Car"**
```bash
db.usuarios.find({ "nombre": { "$regex": "^Car", "$options": "i" } })
```

**2. Buscar usuarios con correos de Gmail**
```bash
db.usuarios.find({ "correo": { "$regex": "@gmail\.com$", "$options": "i" } })
```

**3. Buscar usuarios que viven en ciudades terminadas en "otá"**
```bash
db.usuarios.find({ "ciudad": { "$regex": "otá$", "$options": "i" } })
```

**4. Filtrar usuarios cuyo teléfono empieza en 310**
```bash
db.usuarios.find({ "telefono": { "$regex": "^310" } })
```

**5. Buscar usuarios cuyo rol contenga la palabra "admin"**
```bash
db.usuarios.find({ "rol": { "$regex": "admin", "$options": "i" } })
```

---

## 🛒 Productos

**6. Buscar productos cuyo nombre comience con "Pro"**
```bash
db.productos.find({ "nombre": { "$regex": "^Pro", "$options": "i" } })
```

**7. Filtrar productos con descripciones que mencionen "resistente"**
```bash
db.productos.find({ "descripcion": { "$regex": "resistente", "$options": "i" } })
```

**8. Buscar productos de marcas que terminen en "Sport"**
```bash
db.productos.find({ "marca": { "$regex": "Sport$", "$options": "i" } })
```

**9. Filtrar productos cuyo nombre tenga la palabra "ball"**
```bash
db.productos.find({ "nombre": { "$regex": "ball", "$options": "i" } })
```

**10. Buscar productos con tallas que empiecen por "M"**
```bash
db.productos.find({ "talla": { "$regex": "^M", "$options": "i" } })
```

---

## 📦 Pedidos

**11. Buscar pedidos con ID que empiece en "ORD"**
```bash
db.pedidos.find({ "id_pedido": { "$regex": "^ORD" } })
```

**12. Filtrar pedidos de clientes cuyo nombre tenga "Ana"**
```bash
db.pedidos.find({ "cliente": { "$regex": "Ana", "$options": "i" } })
```

**13. Buscar pedidos con estado "pendiente" (sin importar mayúsculas)**
```bash
db.pedidos.find({ "estado": { "$regex": "pendiente", "$options": "i" } })
```

**14. Buscar pedidos cuya dirección termine en "Colombia"**
```bash
db.pedidos.find({ "direccion": { "$regex": "Colombia$", "$options": "i" } })
```

**15. Filtrar pedidos que tengan referencia de producto que empiece con "PRD"**
```bash
db.pedidos.find({ "productos": { "$elemMatch": { "id_producto": { "$regex": "^PRD" } } } })
```

---

## ⭐ Reseñas

**16. Buscar reseñas que contengan la palabra "excelente"**
```bash
db.reseñas.find({ "comentario": { "$regex": "excelente", "$options": "i" } })
```

**17. Filtrar reseñas donde el usuario empiece por "Juan"**
```bash
db.reseñas.find({ "usuario": { "$regex": "^Juan", "$options": "i" } })
```

**18. Buscar reseñas que terminen con un signo de admiración "!"**
```bash
db.reseñas.find({ "comentario": { "$regex": "!$" } })
```

**19. Filtrar reseñas que mencionen "entrega" en el comentario**
```bash
db.reseñas.find({ "comentario": { "$regex": "entrega", "$options": "i" } })
```

**20. Buscar reseñas de productos cuyo ID empiece por "PRD"**
```bash
db.reseñas.find({ "id_producto": { "$regex": "^PRD" } })
```

---

## 🎟️ Cupones

**21. Buscar cupones cuyo código empiece en "DESC"**
```bash
db.cupones.find({ "codigo": { "$regex": "^DESC" } })
```

**22. Filtrar cupones con códigos que terminen en "2025"**
```bash
db.cupones.find({ "codigo": { "$regex": "2025$" } })
```

**23. Buscar cupones cuya descripción contenga "envío gratis"**
```bash
db.cupones.find({ "descripcion": { "$regex": "envío gratis", "$options": "i" } })
```

**24. Buscar cupones aplicables a categorías que incluyan "ropa"**
```bash
db.cupones.find({ "categorias": { "$regex": "ropa", "$options": "i" } })
```

**25. Filtrar cupones que contengan porcentajes en la descripción ("%")**
```bash
db.cupones.find({ "descripcion": { "$regex": "%" } })
```
---


# 🏆 Conclusión Final

El proyecto **SportShop Online** demuestra cómo las **expresiones regulares en MongoDB** son más que simples consultas:  
son una herramienta poderosa para lograr **búsquedas avanzadas, filtros inteligentes y una experiencia de usuario optimizada**.  

Con la organización clara de colecciones y la implementación de **25 consultas prácticas**, se construye una base sólida que puede escalar fácilmente a un sistema de comercio electrónico real.  

---

> 🌟 **"El conocimiento sin práctica es como un balón sin aire: existe, pero no rueda."** ⚽
---