<a name="readme-top"></a>
# Sesión 1 - Introducción a Big Data y Apache Hadoop

Este repositorio contiene el entorno de desarrollo para la **Sesión 1: Introducción a Big Data y Apache Hadoop** de la asignatura **Ingeniería de Datos: Big Data**, impartida en los másteres de la Escuela Técnica Superior de Ingeniería Informática de la Universidad de Sevilla.

## 🚀 Características

- 📌 Entorno Hadoop desplegado mediante **Docker** y **Docker Compose**.  
- 📁 Ejecución de trabajos **MapReduce** con ejemplos prácticos.  
- 🔍 Acceso completo a **HDFS** desde terminal.  
- 📊 Incluye datasets de prueba para experimentar.  
- 🔄 Entorno modular y fácil de extender.

## 📂 Estructura del Repositorio

```
📂 S1-apachehadoop/
├── 📂 data/
├── 📂 hadoop_config/
├── 📂 scripts/
├── 📂 src/MapReduce/
├── 📄 docker-compose.yml
└── 📄 dockerfile
```

## 🛠️ Requisitos

- **Docker** y **Docker Compose** instalados.  
- **RAM** recomendada: 8GB+  
- **Espacio en disco**: ~5GB para contenedores y datos.

## ⚡ Instalación y Uso

1️⃣ Clona este repositorio del enlace proporcionado por el profesor:  

2️⃣ Inicia el clúster Hadoop:  
```sh
docker-compose up -d
```

3️⃣ Comprueba que los contenedores están activos:  
```sh
docker ps
```

4️⃣ Accede al **Namenode**:  
```sh
docker exec -it namenode bash
```

## 📌 Comandos Útiles en HDFS

```sh
# Listar archivos
hdfs dfs -ls /

# Subir archivo
hdfs dfs -put archivo.txt /ruta/destino/

# Descargar archivo
hdfs dfs -get /ruta/origen/archivo.txt .

# Estado del clúster
hdfs dfsadmin -report

# Salir del modo seguro
hdfs dfsadmin -safemode leave

# Verificar replicación y balanceo
hdfs fsck /
hdfs balancer
```

<p align="right">(<a href="#readme-top">Volver arriba</a>)</p>

## 📝 Notas  

- El sistema está configurado para un entorno de desarrollo, no para producción.  
- Se pueden añadir más **Datanodes** editando el `docker-compose.yml`.  

##  FAQ  
**El namenode me da un error de unexpected end of file**
Verifica caracteres ocultos en el fichero. Ejecuta:
```sh
cat -A start-hdfs.sh
```
Si ves ^M al final de las líneas, el archivo tiene formato Windows y debes convertirlo.
```sh
sed -i 's/\r$//' start-hdfs.sh
```

## 📖 Referencias

- [Documentación oficial de Hadoop](https://hadoop.apache.org/docs/stable/)  
- [Docker Hub – Hadoop Images](https://hub.docker.com/)

<p align="right">(<a href="#readme-top">Volver arriba</a>)</p>