# Simulaciones de rayos cósmicos, transporte de muones y modelado de detectores con ARTI y Meiga

Programa intensivo de formación en simulación de la cadena completa de detección de partículas secundarias producidas por rayos cósmicos: desde su generación en la atmósfera terrestre hasta su propagación a través de la materia y su detección mediante instrumentos instalados a nivel del suelo.

## Tabla de contenidos

- [1. Descripción del curso](#1-descripción-del-curso)
- [2. Duración y formato](#2-duración-y-formato)
- [3. Prerrequisitos](#3-prerrequisitos)
- [4. Objetivo general](#4-objetivo-general)
- [5. Objetivos específicos](#5-objetivos-específicos)
- [6. Sesiones de formación](#6-sesiones-de-formación)
  - [Sesión 1. Rayos cósmicos, cascadas atmosféricas y flujos a nivel del suelo](#sesión-1-rayos-cósmicos-cascadas-atmosféricas-y-flujos-a-nivel-del-suelo)
  - [Sesión 2. Métodos de Monte Carlo y plataforma de simulación ARTI](#sesión-2-métodos-de-monte-carlo-y-plataforma-de-simulación-arti)
  - [Sesión 3. Análisis de catálogos de partículas secundarias generados con ARTI](#sesión-3-análisis-de-catálogos-de-partículas-secundarias-generados-con-arti)
  - [Sesión 4. Transporte de muones a través de la materia e introducción a Meiga](#sesión-4-transporte-de-muones-a-través-de-la-materia-e-introducción-a-meiga)
  - [Sesión 5. Respuesta de detectores y sistemas de detección basados en SiPM](#sesión-5-respuesta-de-detectores-y-sistemas-de-detección-basados-en-sipm)

---

## 1. Descripción del curso

Este programa intensivo de formación introduce las herramientas teóricas y computacionales necesarias para simular la cadena completa de detección de partículas secundarias producidas por rayos cósmicos, desde su generación en la atmósfera terrestre hasta su propagación a través de la materia y su detección mediante instrumentos instalados a nivel del suelo.

El curso se centra en dos plataformas de simulación complementarias:

| Plataforma | Origen | Propósito |
| --- | --- | --- |
| **ARTI** | Colaboración LAGO | Modelar las interacciones de los rayos cósmicos primarios en la atmósfera y generar catálogos realistas de partículas secundarias a nivel del suelo. |
| **Meiga** | Proyecto MuAr (basado en Geant4) | Simular el transporte de muones a través de estructuras complejas y la respuesta de sistemas de detección, incluidos centelladores y fotomultiplicadores de silicio. |

El programa consta de seis sesiones intensivas que combinan clases teóricas, ejercicios computacionales guiados y actividades orientadas a la investigación. Después de completar las sesiones, los participantes desarrollarán un proyecto de investigación individual o grupal que integre ARTI y Meiga para abordar un problema en física de astropartículas, clima espacial, geofísica, desarrollo de detectores o muografía.

## 2. Duración y formato

| Aspecto | Detalle |
| --- | --- |
| Número de sesiones | 6 |
| Duración sugerida por sesión | 4 horas |
| Tiempo total de formación presencial | 24 horas |
| Proyecto de investigación | Entre 4 y 8 semanas |
| Modalidad | Clases teóricas, laboratorios computacionales, discusiones guiadas y trabajo de investigación independiente |
| Nivel | Estudiantes avanzados de pregrado, maestría, doctorado o investigadores en etapas iniciales de su carrera |

Cada sesión deberá incluir aproximadamente:

- **90 minutos** de formación teórica
- **120 minutos** de laboratorio computacional
- **30 minutos** de discusión, interpretación de resultados y preparación del proyecto

## 3. Prerrequisitos

Los participantes deberán contar con:

- Conocimientos básicos de física de partículas o física nuclear
- Conocimientos introductorios sobre rayos cósmicos
- Familiaridad con mecánica clásica y relatividad especial
- Conocimientos básicos de probabilidad y estadística
- Experiencia en programación, preferiblemente en Python
- Manejo básico de Linux y de herramientas de línea de comandos

> [!NOTE]
> La experiencia previa con C++, métodos de Monte Carlo, Geant4, ROOT o computación de alto rendimiento es útil, pero no obligatoria.

## 4. Objetivo general

Proporcionar a los participantes los conocimientos teóricos y las competencias computacionales necesarios para modelar la producción, el transporte y la detección de partículas secundarias generadas por rayos cósmicos, y aplicar estas herramientas en un proyecto de investigación original.

## 5. Objetivos específicos

Al finalizar la formación, los participantes estarán en capacidad de:

1. Explicar el origen y las principales características de los rayos cósmicos primarios y secundarios.
2. Describir el desarrollo de las cascadas atmosféricas extensas.
3. Identificar los factores atmosféricos y geomagnéticos que determinan los flujos de partículas a nivel del suelo.
4. Configurar y ejecutar simulaciones con ARTI en sitios de observación seleccionados.
5. Analizar catálogos de partículas en función de su energía, dirección, tipo y localización geográfica.
6. Describir los mecanismos físicos que rigen la propagación y la pérdida de energía de los muones en la materia.
7. Construir geometrías simplificadas y configuraciones de detectores con Meiga.
8. Simular la deposición de energía y la respuesta de los detectores.
9. Integrar las distribuciones de muones generadas con ARTI en simulaciones realizadas con Meiga.
10. Estimar los flujos de partículas, la aceptación geométrica, la eficiencia de detección, las tasas de eventos y los tiempos de exposición.
11. Evaluar incertidumbres estadísticas y sistemáticas.
12. Formular y ejecutar un proyecto de investigación reproducible.

## 6. Sesiones de formación

### Sesión 1. Rayos cósmicos, cascadas atmosféricas y flujos a nivel del suelo

#### Objetivos

- Introducir las principales preguntas científicas de la física de astropartículas.
- Revisar el origen, la composición y el espectro energético de los rayos cósmicos.
- Comprender la producción de partículas secundarias en la atmósfera.
- Identificar los factores que controlan los flujos de partículas a nivel del suelo.

#### Contenido teórico

- Rayos cósmicos primarios y su espectro energético
- Componentes galáctica, extragaláctica y solar
- Modulación solar
- Interacción de los rayos cósmicos con la atmósfera
- Cascadas electromagnéticas y hadrónicas
- Producción de muones, electrones, fotones, neutrones, piones y kaones
- Profundidad atmosférica y desarrollo de las cascadas
- Dependencia con la altitud, la latitud, el ángulo cenital y las condiciones atmosféricas
- Aplicaciones en física de astropartículas, geofísica, clima espacial y muografía

#### Actividad práctica

Los participantes deberán:

- Analizar espectros representativos de rayos cósmicos primarios.
- Comparar las diferentes componentes de partículas secundarias a nivel del suelo.
- Calcular distribuciones simples de energía y de dirección.
- Estimar la dependencia del flujo de muones atmosféricos respecto del ángulo cenital.
- Seleccionar un sitio de observación para las simulaciones posteriores con ARTI.

#### Producto de la sesión

Una ficha breve de descripción del sitio seleccionado, que incluya:

- Coordenadas geográficas
- Altitud
- Motivación científica
- Partículas secundarias dominantes esperadas
- Posible aplicación en detección o muografía

---

### Sesión 2. Métodos de Monte Carlo y plataforma de simulación ARTI

#### Objetivos

- Introducir los métodos de Monte Carlo empleados en las simulaciones de rayos cósmicos.
- Comprender la estructura y el propósito científico de ARTI.
- Configurar una simulación de cascadas atmosféricas para un sitio seleccionado.

#### Contenido teórico

- Muestreo aleatorio y generación de eventos
- Historias de partículas y pesos estadísticos
- Exposición simulada
- Convergencia estadística
- Modelos de flujo de rayos cósmicos primarios
- Modelos atmosféricos
- Rigidez de corte geomagnética
- Modelos de interacción hadrónica
- Estructura del flujo de trabajo de ARTI
- Etapas modulares de las simulaciones
- Parámetros de entrada, metadatos y catálogos de datos

#### Actividad práctica

Los participantes deberán:

- Instalar o acceder al entorno computacional de ARTI.
- Definir los parámetros geográficos y atmosféricos del sitio seleccionado.
- Seleccionar un modelo de rayos cósmicos primarios.
- Aplicar correcciones geomagnéticas.
- Configurar una simulación reducida con ARTI.
- Examinar el flujo de trabajo y la estructura de los archivos de salida.

#### Producto de la sesión

Un archivo completo de configuración de ARTI y una explicación breve de los parámetros físicos seleccionados.

---

### Sesión 3. Análisis de catálogos de partículas secundarias generados con ARTI

#### Objetivos

- Ejecutar y analizar una simulación con ARTI.
- Caracterizar los flujos de partículas secundarias a nivel del suelo.
- Evaluar los efectos geográficos, atmosféricos y geomagnéticos.

#### Contenido teórico

- Estructura de los catálogos de partículas
- Normalización del flujo
- Tiempo efectivo de simulación
- Espectros de energía
- Distribuciones en ángulo cenital y azimutal
- Clasificación por tipo de partícula
- Comparación entre sitios
- Efectos de presión y temperatura atmosféricas
- Incertidumbres estadísticas y sistemáticas
- Validación mediante modelos analíticos y datos experimentales

#### Actividad práctica

Los participantes deberán:

- Ejecutar o recuperar una simulación realizada con ARTI.
- Separar muones, electrones, fotones, neutrones y otras partículas.
- Construir espectros energéticos diferenciales e integrales.
- Analizar distribuciones angulares.
- Calcular el flujo de muones a nivel del suelo.
- Comparar dos sitios, altitudes o condiciones atmosféricas.
- Preparar la salida de ARTI para utilizarla como fuente de partículas en Meiga.

#### Producto de la sesión

Un informe computacional breve que contenga:

- Espectros de partículas
- Distribuciones angulares
- Estimaciones de flujo
- Comparación entre dos escenarios de simulación
- Análisis inicial de incertidumbres

---

### Sesión 4. Transporte de muones a través de la materia e introducción a Meiga

#### Objetivos

- Comprender los procesos físicos que controlan la propagación de muones.
- Introducir Geant4 y el diseño modular de Meiga.
- Construir un modelo básico de materiales y geometrías.

#### Contenido teórico

- Propiedades relativistas de los muones atmosféricos
- Decaimiento de muones
- Pérdidas de energía por ionización y excitación
- Bremsstrahlung
- Producción de pares
- Interacciones nucleares
- Dispersión múltiple de Coulomb
- Modelos continuos y estocásticos de pérdida de energía
- Alcance de los muones
- Opacidad y densidad integrada
- Geometrías, materiales, partículas y listas de física en Geant4
- Estructura y configuración de Meiga

#### Actividad práctica

Los participantes deberán:

- Definir materiales simples, como roca, concreto, agua y aire.
- Construir un absorbente homogéneo.
- Generar fuentes de muones monoenergéticas y distribuidas.
- Propagar muones a través de diferentes espesores y materiales.
- Calcular las fracciones transmitidas y absorbidas.
- Comparar los resultados simulados con estimaciones analíticas del alcance.

#### Producto de la sesión

Una simulación en Meiga del transporte de muones a través de al menos dos materiales, que incluya la probabilidad de transmisión en función de la energía o del espesor.

---

### Sesión 5. Respuesta de detectores y sistemas de detección basados en SiPM

#### Objetivos

- Modelar la interacción de los muones con los componentes de un detector.
- Calcular la deposición de energía y la eficiencia de detección.
- Comprender la respuesta de sistemas basados en centelladores y SiPM.

#### Contenido teórico

- Deposición de energía en volúmenes activos
- Producción de luz de centelleo y Cherenkov
- Transporte de fotones ópticos
- Geometría y segmentación de detectores
- Principios de funcionamiento de los fotomultiplicadores de silicio
- Eficiencia de detección de fotones
- Ganancia y umbrales electrónicos
- Conteos oscuros, pospulsos y diafonía óptica
- Perfiles temporales de pulsos
- Lógica de coincidencia y sistemas de disparo
- Aceptación geométrica
- Área efectiva y eficiencia de detección

#### Actividad práctica

Los participantes deberán:

- Construir una geometría simplificada de detector en Meiga.
- Simular el paso de muones a través de volúmenes activos.
- Calcular distribuciones de energía depositada.
- Estudiar el efecto del espesor y la orientación del detector.
- Aplicar un umbral de detección.
- Estimar la eficiencia y la aceptación geométrica.
- Comparar dos configuraciones de detector.

#### Producto de la sesión

Un informe de caracterización del detector que incluya:

- Descripción de la geometría
- Espectro de energía depositada
- Eficiencia de detección
- Estimación de la aceptación
- Comparación entre configuraciones alternativas
