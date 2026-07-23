# Actividad de Clase: Analizando Agentes de IA con Hugging Face Spaces

# Ficha de análisis

## 1. Nombre del Space

**Nombre:** Image to 3D Asset with TRELLIS.2

**Enlace:** https://huggingface.co/spaces/microsoft/TRELLIS.2

------------------------------------------------------------------------

## 2. ¿Qué hace el agente?

El agente transforma una imagen bidimensional (2D) en un modelo tridimensional (3D) exportable en formato .glb. Ajustando parámetros como la resolución, el número de polígonos y las pasadas de muestreo. Este se puede usar en proyectos de diseño, videojuegos o animación.

------------------------------------------------------------------------

## 3. Análisis PEAS

  Elemento          Respuesta
  ----------------- ----------------------------------------------------
  **Performance**   Exactitud con la que el activo 3D reconstruye el objeto 2D original, calidad estética de las texturas y generación exitosa del archivo .glb en tiempos razonables.
  **Environment**   Como este agente no es un robot físico, su entorno es virtual. Puede ser la interfaz de la página web o el sistema de procesamiento en la nube.
  **Actuators**     Crea y entrega el archivo descargable para programas de diseño 3D.
  **Sensors**       Recibe la imagen como entrada y una serie de configuraciones que puede proponer el usuario como la semilla, resolución, textura, etc.

------------------------------------------------------------------------

## 4. Clasificación del entorno

Complete la siguiente tabla y justifique brevemente cada respuesta.

  Propiedad      Clasificación     Justificación
  -------------- ----------------- ---------------
  **Observable**     Parcial            El agente solo observa una proyección 2D del objeto. No conoce la parte trasera ni la geometría del objeto original; debe inferir las partes ocultas.
  **Determinista**   No                 La generación utiliza ruido aleatorio controlado por la semilla (Seed). Variar la semilla o el proceso de muestreo genera resultados geométricos diferentes para la misma imagen.
  **Episódico**      Sí                 Cada imagen es una prueba independiente. La experiencia de convertir un objeto previo no modifica el procesamiento ni los datos del siguiente episodio.
  **Estático**       Sí                 La imagen cargada y los parámetros seleccionados no cambian de forma dinámica por sí solos mientras el agente realiza sus cálculos.           
  **Discreto**       Sí                 La imagen de entrada tiene un número finito y medible de píxeles. Además, todos los controles de la interfaz operan con valores enteros o selecciones fijas (pasos de muestreo del 1 al 50, semillas numéricas enteras y resoluciones predefinidas como 512, 1024 o 1536).
  **Conocido**       Sí                 Las reglas del entorno (las operaciones matemáticas del modelo y las restricciones de la física 3D previa) están completamente codificadas en la red neuronal.          

------------------------------------------------------------------------

## 5. ¿Qué tipo de programa de agente creen que es?

Opción seleccionada: Agente basado en modelo.
Justificación: Dado que una foto plana no muestra la parte trasera ni el volumen de los objetos, un agente de reflejo simple fallaría por completo al no poder reaccionar a lo que no ve. Por eso, para reconstruir el objeto completo, el agente consulta sobre la geometría 3D, formas y texturas aprendidas durante su entrenamiento. Por último, combina la entrada actual (la imagen) con su modelo para deducir la estructura completa del objeto y generar una figura tridimensional coherente que se puede observar desde cualquier ángulo.

------------------------------------------------------------------------
# Discusión en clase

Después de las presentaciones, discutiremos preguntas como:

-   ¿Dos Spaces diferentes pueden compartir el mismo tipo de entorno? Sí. Las propiedades del entorno las define la naturaleza del problema y la interfaz, no la arquitectura del modelo.
-   ¿Es posible saber con certeza qué tipo de agente implementa un Space
    únicamente observándolo? No. Desde el exterior (caja negra) solo observamos entradas y salidas. Un script complejo podría imitar externamente el comportamiento de un agente basado en modelo.
-   ¿Qué diferencia existe entre el comportamiento observable de un
    agente y su implementación interna? El comportamiento observable es lo que hace el agente (su respuesta visible en la interfaz), mientras que la implementación interna es el cómo lo logra (los algoritmos, código y arquitectura de red neuronal).

------------------------------------------------------------------------

# Reto adicional

Encuentre un Space que pueda clasificarse como:

1.  **Totalmente observable, determinista y episódico.**
   Un detector de objetos por imágenes: Se ve toda la imagen (totalmente observable), la misma foto siempre da la misma etiqueta si los pesos están fijos (determinista) y cada imagen es independiente de las demás (episódico).
3.  **Parcialmente observable, estocástico y secuencial.**
   Un chatbot con memoria: No conoce el estado interno ni las intenciones completas del usuario (parcialmente observable), sus respuestas varían (estocástico) y las acciones actuales condicionan directamente la historia o el estado futuro (secuencial).

------------------------------------------------------------------------

# Rúbrica (10 puntos)

| Criterio | Puntos |
|-----------|:------:|
| Descripción correcta del Space | 2 |
| Identificación de PEAS | 3 |
| Clasificación del entorno | 3 |
| Justificación del tipo de agente | 2 |
| **Total** | **10** |

------------------------------------------------------------------------
