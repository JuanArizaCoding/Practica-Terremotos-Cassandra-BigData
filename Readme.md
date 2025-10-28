# 🐍 Configuración del entorno virtual y Cassandra con Docker

En este documento se detallan los pasos para conseguir levantar correctamente
**Cassandra** usando **Docker Compose**, y el entorno virtual donde irán asociadas
todas las dependecias.

---

## 🚀 1. Crear el entorno virtual

Primero abre una terminal en WSL, navega hasta el directiro raíz `practica-bbdd` y crea un entorno virtual llamado `cassandra-venv`:

```bash
python3 -m venv cassandra-venv
```

## ⚙️ 2. Activar el entorno virtual

Activa el entorno virtual recién creado:

```bash
source cassandra-venv/bin/activate
```

> [!NOTE]  
> 💡 **Nota:** Cada vez que abras una nueva terminal, deberás volver a activar el entorno virtual antes de ejecutar cualquier comando relacionado con el proyecto.

## 📦 3. Actualizar pip e instalar dependencias

Con el entorno virtual activo en la terminal, instala las dependencias necesarias:

```bash
pip install --upgrade pip -q
pip install pexpect cassandra-driver pandas pycountry
```

## 🐳 4. Levantar Cassandra con Docker

Accede a la carpeta donde se encuentra el archivo `docker-compose.yml`:

```bash
cd docker-cassandra/
```

Luego levanta el contenedor de Cassandra:

```bash
docker compose up -d
```

## 💻 5. Configurar el entorno en VS Code

Para asegurarte de que VS Code utiliza el entorno virtual `cassandra-venv`:
1. Presiona `Ctrl + Shift + P` en Windows o `Cmd + Shift + P` en macOS.
2. Escribe y selecciona `Python: Select Interpreter`.
3. Elige el intérprete que corresponde a `cassandra-venv`.


## 🧱 Estructura recomendada del proyecto

```bash
project/
├── cassandra-venv/
├── data/
│   └── earthquake_data_tsunami.csv
├── docker-cassandra/
│   └── docker-compose.yml
├── Actividad_BDNoSQL_2025.pdf
├── practica_2_cassandra.ipynb
└── README.md
```