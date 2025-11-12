# Python Aplicado a la Ingeniería

Universidad Pontificia Bolivariana

**Docente:** Miguel Ortiz Padilla

## Repositorio con las soluciones de las evaluaciones del curso

**Estudiantes:** Samuel Andres Gonzalez Negrete - Alejandro Gonzalez Diaz - Damaso Doria Fara

**Correos:** samuel.gonzalezn@upb.edu.co - alejandro.gonzalezd@upb.edu.co - damaso.doria@upb.edu.co

## Proyecto final

**Objetivo:** Desarrollar un sistema funcional de Visión Computacional en Python para la identificación y registro de placas de vehículos (ANPR), utilizando la cámara del dispositivo o imágenes cargadas. (El proyecto simula un escenario real de captura, procesamiento y extracción de caracteres alfanuméricos).

**Descripción técnica:** El sistema implementa un flujo de trabajo de Visión por Computadora y Reconocimiento Óptico de Caracteres (OCR) con una interfaz de menú simple para el usuario. El sistema sigue los siguientes pasos de forma secuencial:

- Captura/Carga: El usuario selecciona entre captura en vivo (cámara web) o carga de archivo (Opción 1 y 2).

- Pre-procesamiento: Se aplica filtrado bilateral (para ruido), detección de bordes Canny, y cierre morfológico para asegurar la continuidad del contorno de la placa.

- Detección de Contorno (ROI): Se buscan contornos de 4 lados (rectangulares) que cumplan con una relación de aspecto y área permisiva, optimizada para placas.

- Optimización para OCR: El recorte de la placa es escalado y sometido a Ecualización de Histograma Adaptativa (CLAHE), reducción de ruido y un filtro de Afilado (Sharpening) para mejorar la nitidez.

- Extracción OCR y Votación: Se utiliza la librería Tesseract para intentar la lectura con múltiples configuraciones (PSM 7, PSM 8, e imagen invertida). El resultado se elige por un sistema de votación que devuelve la placa más frecuente y su nivel de confianza.

- Almacenamiento: El resultado final (Placa, Fecha, Hora de Colombia y Nivel de Confianza) se registra en el archivo registro_placas_vehiculos.csv.

**Dependencias:** El proyecto está desarrollado en Python y requiere las siguientes librerías para su ejecución:

. OpenCV (cv2): Pre-procesamiento de imagen, detección de contornos, recortes (ROI) y filtros.

. pytesseract: Motor de Reconocimiento Óptico de Caracteres (OCR).

. Tesseract-OCR: Motor externo de OCR requerido por pytesseract.

. pandas: Manejo y persistencia de los datos en el archivo registro_placas_vehiculos.csv.

. pytz: Manejo de zonas horarias para registrar la hora local de Colombia (America/Bogota).

. numpy: Manejo de arreglos y matrices de imágenes.

**Ejecución:** 

1. Clonar el Repositorio
2. Abrir en Google Colab
3. Ejecución: Ejecutar todas las celdas del notebook en orden. El sistema instalará automáticamente las dependencias necesarias (OpenCV, Tesseract, pytesseract, pytz) al inicio
4. Menú: Aparecerá un menú interactivo
5. Salida: Los resultados se almacenarán en registro_placas_vehiculos.csv y se mostrarán en pantalla.
