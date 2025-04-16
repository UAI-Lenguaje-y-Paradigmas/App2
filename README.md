# **TICS200: App #2 – Gestión Agrícola en Java (POO)**

## **Profesores**
- **María Loreto Arriagada**  
  loreto.arriagada.v@edu.uai.cl

- **Paulina González**  
  paulina.gonzalez.p@edu.uai.cl

- **Justo Vargas**  
  justo.vargas@edu.uai.cl

## **Ayudante**
- **Diego Duhalde**  
  dduhalde@alumnos.uai.cl

---

## 1. Objetivos

1. **Estructurar** un programa en Java siguiendo principios de la **Programación Orientada a Objetos (POO)**:  
   - Herencia  
   - Encapsulamiento  
   - Paquetes  
   - Composición  
   - Interfaces  
   - Abstracción  
2. **Persistir datos** a un archivo CSV, manejando lectura y escritura de información.  
3. Practicar **herramientas de apoyo** a la programación: GIT (fork, pull requests, commits balanceados), debuggers, etc.

---

## 2. Enunciado

Imaginemos que una empresa agrícola necesita un **software de gestión de cultivos**. El objetivo es mantener un registro de los cultivos, parcelas, y actividades de mantenimiento. Al iniciar el programa, se leerá un archivo CSV (`cultivos.csv`) que representa el estado inicial del sistema. Al finalizar, todos los cambios se guardarán nuevamente en el mismo archivo.

### 2.1 Requerimientos funcionales

El programa debe:

1. Iniciarse desde la consola con:  
   ```bash
   java App2 cultivos.csv
   ```
   donde App2.java es la clase principal y cultivos.csv el archivo de persistencia.

2. Presentar un menú principal en consola, que permita acceder a las siguientes funciones:

   - **Gestión de Cultivos**
     - Listar cultivos existentes.
     - Crear un nuevo cultivo.
     - Eliminar un cultivo (solo si no tiene actividades pendientes).
     - Editar la información básica de un cultivo (nombre, variedad, fecha de siembra, etc.).

   - **Gestión de Parcelas**
     - Listar parcelas con sus cultivos.
     - Agregar una parcela.
     - Eliminar una parcela (solo si no tiene cultivos activos).
     - Editar una parcela (cambiar tamaño, ubicación, etc.).
     - Asignar un cultivo a una parcela.

   - **Gestión de Actividades**
     - Registrar actividad (riego, fertilización, cosecha, etc.) para un cultivo.
     - Listar actividades por cultivo.
     - Eliminar actividad.
     - Marcar actividad como completada.

   - **Búsqueda/Reporte**
     - Buscar cultivos por nombre o variedad (mostrar datos relevantes).
     - Reporte de cultivos activos, cosechados, o en riesgo.

   - **Salir**
     - Guardar toda la información en cultivos.csv y finalizar el programa.

### 2.2 Supuestos y detalles

- Cada parcela puede tener múltiples cultivos.
- Al menos una clase abstracta o interfaz debe emplearse para representar algún concepto genérico (por ejemplo, "ElementoAgrícola" que represente algo con nombre, fecha y estado).
- Se sugiere utilizar colecciones de Java (ArrayList, HashMap, List, etc.) para administrar cultivos, parcelas, actividades, etc.
- El usuario ingresa "información válida" (no se requiere validación exhaustiva).
- No hay campos vacíos en el CSV al iniciar.
- Se evaluará el uso de herencia, encapsulamiento y paquetes para organizar las clases (por ejemplo, un paquete models, otro services, etc.).

### 2.3 Formato del CSV

El formato del CSV será sencillo y consistente, todas las líneas tendrán la misma estructura:

```
Cultivo,"Maíz","Variedad Dulce",32.5,"PARCELA-A01","2023-03-01","ACTIVO",["RIEGO:2023-03-10","FERTILIZACION:2023-03-20"]
Cultivo,"Trigo","Variedad Premium",45.2,"PARCELA-B03","2023-02-15","ACTIVO",["RIEGO:2023-02-25","COSECHA:2023-06-15"]
Cultivo,"Tomate","Cherry",10.0,"PARCELA-C02","2023-04-05","EN_RIESGO",["FUMIGACION:2023-04-20"]
Cultivo,"Lechuga","Romana",8.5,"PARCELA-A02","2023-03-10","COSECHADO",["RIEGO:2023-03-20","COSECHA:2023-05-01"]
```

Cada línea contiene:
- Tipo de registro (siempre "Cultivo")
- Nombre del cultivo
- Variedad
- Superficie (hectáreas)
- Código de parcela
- Fecha de siembra
- Estado (ACTIVO, EN_RIESGO, COSECHADO)
- Lista de actividades con fechas (formato JSON simple)

## 3. Nuevos Requerimientos y Detalles de la Entrega

- **Lenguaje**: Java (versión 16 o superior, u OpenJDK 16+).
- **Grupos**: 4 o 5 personas (no se admitirán grupos de 6).
- **Fecha de entrega**: Sábado 3 de Mayo a las 23:59.
- Por cada día de atraso se descuenta 1 punto, comenzando a las 00:00 del día siguiente.
  - Ejemplo: si entregan a las 00:00 del día siguiente, la nota máxima es 6.0.

### Opcional: Diagrama de Clases

Deben entregar un diagrama de clases que represente su solución:

- Cardinalidades (ej. una parcela tiene N cultivos, un cultivo tiene M actividades, etc.)
- Herencia (si usan clases que extiendan de alguna clase base)
- Interfaces (si las usan)
- Composición o agregación (por ejemplo, una parcela contiene un conjunto de cultivos).

Se evaluará en particular el uso correcto de:

- Paquetes (organizar las clases en paquetes coherentes).
- Modificadores de Acceso (privado, público, protegido) y encapsulamiento.
- Herencia (si se crea una superclase ElementoAgricola o un patrón similar).
- Colecciones (ArrayList, List, Map, etc.).
- Interfaces/Clases abstractas (al menos un uso sensato).

## 4. Formato de Entrega (vía repositorio GitHub)

### Repositorio de trabajo

- Deberán crear un repositorio para el grupo que se llame App2 en GitHub (o el que indique el curso).
- Asegurarse que el repositorio sea privado al grupo de trabajo.
- En ese repositorio, agregar a todos los integrantes del grupo como colaboradores, y dar acceso a dicho repositorio al profesor y al ayudante.

### Commits balanceados y Pull Request

- Cada integrante del grupo debe tener aproximadamente la misma cantidad de commits.
- Se evaluará la participación equitativa a través del historial de commits.
- La entrega oficial por medio de WEBC indicando la URL del repo (o como indique la asignatura).

### Estructura del repositorio

- Código fuente en Java, organizado en paquetes (models, services, ui, etc.).
- Diagrama de clases (en formato imagen/PDF).
- Informe de diseño (PDF o Markdown) con:
  - Arquitectura (clases, paquetes, herencia, etc.).
  - Justificación del uso de colecciones y patrones de diseño (si aplican).
  - Manejo de modificadores de acceso.
  - Reflexiones finales / autoevaluación:
    - ¿Qué fue lo más desafiante de implementar en POO?
    - ¿Cómo controlaron la lectura y escritura de CSV?
    - ¿Qué aprendizajes surgieron del proyecto?
  - Explicación de uso de IA (si aplica):
    - ¿Qué tipo de ayuda proporcionó la herramienta?
    - ¿Cómo validaron o contrastaron las sugerencias?
- README explicando cómo compilar/ejecutar el programa, con info de cada integrante (nombre, correo, etc.).

### Compilación y ejecución

- Desde la raíz del proyecto, se debe poder compilar (por ejemplo, javac App2.java u otro comando, dependiendo de la estructura).
- Luego, ejecutar:
  ```bash
  java App2 cultivos.csv
  ```
- El programa mostrará un menú que permita realizar las acciones mencionadas (crear cultivo, registrar actividad, buscar, etc.).
- Al salir, se guardarán los cambios en cultivos.csv.

## 5. Rúbrica de Evaluación

| Criterio | Peso | Descripción |
|----------|------|-------------|
| 1. Funcionamiento general | 30% | <ul><li>El proyecto compila y se ejecuta correctamente.</li><li>Menús y submenús funcionan sin errores ni excepciones no controladas.</li><li>Guardado y lectura de cultivos.csv se realizan de forma coherente.</li></ul> |
| 2. Paradigma Orientado a Objetos | 30% | <ul><li>Uso adecuado de clases, encapsulamiento, herencia, interfaces y colecciones.</li><li>Organización en paquetes clara y lógica.</li><li>Aplicación de principios de OOP (mínima duplicación de código, coherencia en la jerarquía de clases, etc.).</li></ul> |
| 3. Informe de diseño y reflexiones finales | 10% | <ul><li><strong>Informe de diseño</strong>: explica la arquitectura, justifica las decisiones (7%).</li><li><strong>Reflexiones</strong>: aprendizajes, desafíos, etc. (5%).</li><li><strong>Uso de IA</strong>: transparencia y validación (3%).</li></ul> |
| 4. Uso de Git (commits y pull request) / Organización del repositorio/Presentación | 20% | <ul><li>Commits equilibrados entre integrantes (aporte individual visible).</li><li>Estructura del repositorio clara, con README que indique cómo compilar/ejecutar.</li></ul> |
| 5. Presentación | 10% | <ul><li>Presentar en clases la solución la app</li><li>Presentar la app funcionando.</li></ul> |
| **Total** | **100%** |  |

### Penalizaciones y Bonus

- **Atrasos**: Resta 1 punto al máximo posible por día de atraso (comenzando a las 00:00 del día siguiente).
- **Grupos con más de 5 integrantes**: penalización (no se admite grupo de 6).
- **Grupos con menos integrantes**: puede existir un pequeño bonus, según políticas de la asignatura.
- **Arquitectura y diagrama de clases**: puede existir un pequeño bonus, según políticas de la asignatura (Diagrama de clases con cardinalidades y relaciones (herencia, composición, etc.)).

## 6. Ejemplo de Uso

```bash
# (1) Clonar/forkear el repositorio
git clone https://github.com/<usuario>/App2.git

# (2) Compilar
cd App2
javac src/*.java

# (3) Ejecutar
java src/App2 cultivos.csv
```

Se mostrará un menú en consola que permitirá:
- Listar cultivos
- Crear/editar/eliminar un cultivo
- Agregar/editar parcelas
- Registrar actividades
- Buscar cultivos/parcelas
- etc.

Al seleccionar "Salir", se guardarán los cambios en cultivos.csv.

## 7. Conclusión

Este App #2 busca afianzar conocimientos de POO en Java, lectura/escritura de CSV, y la correcta aplicación de principios de diseño (herencia, encapsulamiento, interfaces, composición). Aseguren una arquitectura clara, un diagrama de clases que refleje su solución, y un uso equilibrado de GIT para evidenciar la contribución de cada integrante.
