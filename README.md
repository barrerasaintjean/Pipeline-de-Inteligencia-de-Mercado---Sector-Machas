# 🐟 Proyecto: De la necesidad de vender al Análisis de Datos

### 📖 La Historia 
Todo empezó con una pregunta difícil: **¿Cómo salgo a vender si no sé por dónde empezar?** Actualmente estoy estudiando para ser **Analista de Datos** y me encontré con dos problemas al mismo tiempo. Primero, necesitaba una base de datos real de posibles clientes (pescaderías en Santiago) para salir más confiado sabiendo cómo nos posicionamos ante la competencia o también pensaba en generar mensajes automáticos para hacer el contacto. Segundo, estaba cansado de practicar SQL con tablas de ejemplo "de juguete"; quería datos reales, vivos y extraídos por mí mismo.

Yo ya sabía que gente ocupaba bots para sacar información de la web, así que decidí aprender con ayuda de la IA.

---

### 🛠️ ¿Qué hice y por qué usé estas herramientas?

1. **n8n (El Automatizador):** Es el corazón del proyecto. En lugar de programar cada conexión desde cero, usé n8n para conectar la API de Google Maps con mi base de datos. Fue un desafío porque tuve que aprender a manejar errores de "campos vacíos" (locales sin web) y filtrar duplicados. Primero se intentó con Python, pero las webs me bloqueaban muy fácil y no lograba sacar la información.
2. **PostgreSQL (La Memoria):** Aquí es donde pongo en práctica lo que estudio. Usé una base de datos relacional para guardar todo de forma estructurada. Aprendí a crear tablas simples y apliqué *Unique Constraints* para que la base de datos misma rechace datos repetidos si el robot falla.
3. **Docker (Mi maleta técnica):** Instalé Postgres a través de Docker porque no quería ensuciar mi PC con instalaciones pesadas. Lo mejor es que si cambio de computador, simplemente me llevo mis archivos de configuración; lo encontré interesante por si alguna vez quiero crear una base de datos con una Raspberry Pi.
4. **DBeaver (La Ventana):** Es mi herramienta para hablar con los datos. Aquí es donde ejecuto mis queries de SQL para limpiar la tabla y verificar que todo entró bien.

---

### 🔄 El Diagrama del Flujo
1. **Google Maps (SerpApi)** suelta los datos brutos.
2. **n8n** recibe el paquete de 20 locales, quita los que están repetidos y se asegura de que el formato sea el correcto (este punto se piensa mejorar, 20 locales es muy poco para una base de datos).
3. **Postgres (dentro de Docker)** recibe la lista limpia. Si el local ya existe, lo actualiza; si es nuevo, lo crea.
4. **DBeaver** es donde yo entro a interrogar a la base de datos para preparar mi ruta de ventas.

---

### 🚀 Esto no termina aquí (Próximos pasos)
Este es solo mi **MVP (Producto Mínimo Viable)**. Lo que tengo ahora es una base sólida, pero mis planes son:
* **Escalar la búsqueda:** Santiago es gigante. Voy a programar un barrido automático por cada comuna (Las Condes, Maipú, Puente Alto, etc.); la verdad pienso buscar las comunas que estén en el camino del despacho, para así hacer más eficientes los días de despacho.
* **Graficar la competencia:** Quiero conectar estos datos a un panel visual. Mi meta final es ver en un mapa dónde estoy yo y dónde está mi competencia, ya que la información es vital cuando uno quiere negociar.

---

**Hecho con ☕, hiperfoco y ganas de aprender a automatizar.**
