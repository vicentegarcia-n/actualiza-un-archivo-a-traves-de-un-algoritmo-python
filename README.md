# actualiza-un-archivo-a-traves-de-un-algoritmo-python
Proyecto hecho en el curso #7 "Automatiza las tareas de ciberseguridad con Python" del Certificado de Ciberseguridad de Google

### 🐍 Actualiza un archivo a través de un algoritmo Python

**Descripción:**  
Este proyecto presenta un **algoritmo en Python** que gestiona el acceso a registros sensibles en una organización del sector de salud. Se desarrolló un script que **automatiza la actualización de una lista de direcciones IP autorizadas**, eliminando aquellas que ya no deberían tener acceso a la red restringida.  

**📌 Objetivo del proyecto:**  
- **Leer** un archivo de texto con direcciones IP autorizadas.  
- **Comparar** las direcciones IP con una lista de eliminación (`remove_list`).  
- **Eliminar** las direcciones no autorizadas.  
- **Actualizar** el archivo con la nueva lista de direcciones permitidas.  

**🛠️ Pasos de implementación:**  

1. **📂 Abrir y leer el archivo con IPs permitidas:**  
   - Se utilizó `with open("allow_list.txt", "r")` para abrir el archivo en modo lectura.  
   - Se empleó `.read()` para almacenar el contenido en una variable.  

2. **🔄 Convertir la cadena en una lista:**  
   - Se usó `.split()` para transformar la cadena en una lista de direcciones IP.  

3. **🔍 Iterar y eliminar direcciones no autorizadas:**  
   - Se recorrió la `remove_list` con un bucle `for`.  
   - Se aplicó `.remove()` para eliminar coincidencias en la lista principal.  

4. **📌 Convertir la lista actualizada en cadena y sobrescribir el archivo:**  
   - Se utilizó `join()` para reconvertir la lista en una cadena.  
   - Se abrió el archivo en **modo escritura (`"w"`)** y se utilizó `.write()` para actualizar el contenido.  

**📜 Código principal:**  

```python
# Abrir y leer la lista de IPs permitidas
with open("allow_list.txt", "r") as file:
    ip_addresses = file.read().split()

# Lista de IPs a eliminar
remove_list = ["192.168.1.10", "192.168.1.20"]

# Eliminar las IPs no autorizadas
for ip in remove_list:
    if ip in ip_addresses:
        ip_addresses.remove(ip)

# Sobrescribir el archivo con la lista actualizada
with open("allow_list.txt", "w") as file:
    file.write(" ".join(ip_addresses))
```
**🔧 Herramientas utilizadas:**

- **Python** para el desarrollo del algoritmo.
- **Manejo de archivos (`open`, `read`, `write`)** en Python.
- **Manipulación de listas (`split`, `join`, `remove`)** para actualizar la información.

**📌 Aprendizajes clave:**

- Cómo **automatizar la actualización de archivos** en Python.
- Uso de **métodos de manipulación de cadenas y listas** en Python.
- Aplicación de **control de acceso mediante listas de permisos** en un entorno de ciberseguridad.
