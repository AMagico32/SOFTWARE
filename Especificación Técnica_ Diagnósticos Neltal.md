# Especificación Metodológica de Diagnósticos Neltal

### Guía de Variables, Lógicas de Transmisión y Requerimientos de Modelado Matemático

Este documento sistematiza la estructura operativa e ideológica de los tres niveles de diagnóstico de **Neltal** (Básico, Intermedio y Avanzado). Su propósito es servir como el plano de requisitos lógicos para el codiseño y desarrollo de modelos matemáticos, algoritmos de optimización y arquitecturas de datos que se integrarán en el núcleo del software de Neltal.

## ESTRUCTURA METODOLÓGICA GENERAL

El motor analítico de Neltal opera bajo una premisa fundamental: **la vulnerabilidad microeconómica es el resultado de la pérdida de soberanía operativa frente a factores de extracción (intermediarios parasitarios) y rigideces estructurales**.

Para cuantificar y modelar esta realidad, dividimos la intervención en tres etapas progresivas:

┌─────────────────────────────────────────────────────────────┐  
│ 1. DIAGNÓSTICO BÁSICO: Supervivencia y Flujo de Caja │  
│ (Modelado cualitativo-conductual, fugas y caja única) │  
└──────────────────────────────┬──────────────────────────────┘  
▼  
┌─────────────────────────────────────────────────────────────┐  
│ 2. DIAGNÓSTICO INTERMEDIO: Estabilidad y Margen Operativo │  
│ (Optimización de portafolio, canales y costo financiero) │  
└──────────────────────────────┬──────────────────────────────┘  
▼  
┌─────────────────────────────────────────────────────────────┐  
│ 3. DIAGNÓSTICO AVANZADO: Soberanía Territorial y Macro-Micro │  
│ (Geointeligencia, optimización fiscal e impacto macro) │  
└─────────────────────────────────────────────────────────────┘  

## NIVEL 1: DIAGNÓSTICO BÁSICO (Supervivencia y Flujo Inmediato)

### 1\. Objetivo del Modelado

Estabilizar de forma inmediata la caja del micronegocio popular (autoempleo o microempresa de subsistencia). En este nivel, la carencia de registros históricos estructurados obliga a trabajar con **narrativas de campo, estimaciones estocásticas y variables conductuales**.

### 2\. Componentes Analíticos y Variables a Modelar

#### A. El Fenómeno de "Caja Única" (Subsidio Cruzado Hogar-Negocio)

- **El Problema:** El dueño no asigna un salario a su trabajo y mezcla el flujo de efectivo del negocio con el presupuesto del hogar, lo que genera una ilusión de liquidez que enmascara una quiebra técnica.
- **Variables de Entrada:**
    - Ingresos diarios estimados ().
    - Retiros discrecionales diarios para consumo del hogar ().
    - Costo de reposición estimado del trabajo del dueño (: cuánto costaría contratar a un tercero para hacer su labor).
    - Gastos compartidos indivisos (: luz, gas, renta de espacios compartidos hogar/negocio).
- **Reto Matemático para el Profesor:** Formular una ecuación de **Costo de Producción Real** que incorpore el costo de oportunidad del trabajo familiar y determine el nivel de subsidio implícito. Necesitamos modelar la frontera del flujo de efectivo:  
    Donde  es el coeficiente de prorrateo del gasto compartido que el modelo debe estimar.

#### B. Mapa de Fugas de Capital Hormiga e Intermediación Trivial

- **El Problema:** Pérdidas no registradas por mermas, microcomisiones por uso de terminales mal configuradas, cobros hormiga de proveedores locales u obsolescencia de inventarios.
- **Variables de Entrada:**
    - Frecuencia de surtido ().
    - Volumen de merma percibida vs. merma real calculated por diferencia de inventarios.
    - Costo unitario de adquisición al menudeo vs. costo potencial a medio mayoreo.
- **Reto Matemático para el Profesor:** Diseñar un modelo de **Vulnerabilidad por Dispersión**. Dado que el micronegocio compra insumos diariamente al menudeo, el modelo debe calcular la pérdida de eficiencia por no consolidar inventario, formulando un EOQ (_Economic Order Quantity_) adaptado a un flujo de caja sumamente restringido.

#### C. Parametrización del Sesgo Conductual (Economía del Comportamiento)

- **El Problema:** La resistencia psicológica del comerciante a llevar registros o adoptar tecnologías debido al sesgo del presente, miedo al fisco o desconfianza en algoritmos.
- **Variables de Entrada (Cualitativas Escala Likert):**
    - Nivel de digitalización actual ().
    - Hábito de registro de transacciones ().
    - Aversión declarada al control fiscal ().
- **Reto Matemático para el Profesor:** Construir una **Matriz de Probabilidad de Adopción (Markov / Redes Bayesianas)**. Queremos calcular la probabilidad de que el comerciante ejecute con éxito el "Plan de Choque de 72 Horas" basándonos en sus rasgos psicológicos y operativos.

## NIVEL 2: DIAGNÓSTICO INTERMEDIO (Estabilidad, Canales y Operación)

### 1\. Objetivo del Modelado

Optimizar la estructura financiera interna y evaluar la eficiencia de la mezcla de productos y los canales de venta en PyMEs que ya poseen registros históricos mínimos (estados de cuenta, notas de venta o sistemas POS básicos).

### 2\. Componentes Analíticos y Variables a Modelar

#### A. Optimización de Portafolio y Mezcla de Ventas (Pareto Avanzado)

- **El Problema:** El negocio asume que el producto que más volumen vende es el más rentable. Sin embargo, suele ser un "producto ancla" con margen de contribución marginal, mientras que productos de baja rotación pero alto margen están subexplotados.
- **Variables de Entrada:**
    - Precio de venta unitario por producto  ().
    - Costo variable unitario por producto  ().
    - Volumen de ventas mensual por producto  ().
    - Espacio/tiempo de almacenamiento ocupado por el inventario del producto .
- **Reto Matemático para el Profesor:** Formular un problema de **Programación Lineal con Restricciones** para maximizar el margen de contribución global bajo restricciones de capital de trabajo y capacidad operativa física:  
    Sujeto a:

#### B. Análisis Financiero de Pasivos y Costo del Crédito Comercial/Fintech

- **El Problema:** Las PyMEs mexicanas suelen financiarse con microcréditos "gota a gota", terminales de cobro con adelanto de ventas o créditos Fintech con tasas de interés diario que licuan sus ganancias.
- **Variables de Entrada:**
    - Capital insoluto de deudas vigentes ().
    - Frecuencia de amortización (diaria, semanal, quincenal).
    - Comisiones de apertura y seguros obligatorios.
- **Reto Matemático para el Profesor:** Desarrollar un algoritmo que calcule la **Tasa Efectiva Anual Real ()** incorporando la frecuencia de capitalización y las comisiones ocultas, comparando este costo financiero contra el Margen de Utilidad Operativa del negocio para determinar el grado de asfixia financiera:  
    El modelo debe simular el impacto del pago de deuda en la probabilidad de insolvencia de la PyME en un horizonte de 6 meses.

#### C. Eficiencia del Canal y Extracción de Rentas (Fase 1 IVN)

- **El Problema:** Evaluar la rentabilidad real de vender a través de agregadores (UberEats, Rappi, MercadoLibre) versus canal físico propio.
- **Variables de Entrada:**
    - Ventas por canal digital () y físico ().
    - Tasa de comisión del canal digital ().
    - Gasto en publicidad pagada en la plataforma ().
    - Costo de empaque especial e insumos adicionales para envíos.
- **Reto Matemático para el Profesor:** Modelar el **Umbral de Viabilidad de Intermediación**. Definir algebraicamente en qué punto porcentual de dependencia del canal digital el costo de adquisición de clientes () supera al costo operativo físico, destruyendo el margen neto de la empresa.

## NIVEL 3: DIAGNÓSTICO AVANZADO (Estratégico, Territorial y Macroeconómico)

### 1\. Objetivo del Modelado

Blindar la competitividad del negocio en su territorio mediante el cruce de datos internos con variables macroeconómicas mexicanas y modelos de geointeligencia comercial, preparando el terreno para la integración vertical al conglomerado Neltal.

### 2\. Componentes Analíticos y Variables a Modelar

#### A. Geointeligencia Territorial y Competencia (Modelo de Huff Modificado)

- **El Problema:** El negocio opera a ciegas ante las fuerzas gravitacionales del mercado local (ej. la apertura de un competidor corporativo como un OXXO o un supermercado en su radio de influencia).
- **Variables de Entrada:**
    - Coordenadas geográficas del negocio y sus competidores directos e indirectos (extraídos vía API del DENUE - INEGI).
    - Superficie o capacidad estimada de cada punto de venta ().
    - Distancia de viaje o tiempo de traslado del consumidor  al negocio  ().
- **Reto Matemático para el Profesor:** Aplicar el **Modelo Gravitacional de Huff** para predecir la probabilidad () de que un cliente del territorio visite el negocio de nuestro aliado en lugar de la competencia corporativa:  
    Donde  es el parámetro de fricción de la distancia en el contexto urbano mexicano. El modelo debe calcular la pérdida de participación de mercado proyectada ante la entrada de nuevos competidores.

#### B. Optimización de la Estructura de Costos Duros e Impacto Fiscal

- **El Problema:** Evaluación del impacto real de la transición fiscal (ej. migrar de la informalidad al Régimen Simplificado de Confianza - RESICO o a Persona Física con Actividad Empresarial) sobre la liquidez neta del negocio.
- **Variables de Entrada:**
    - Ingresos brutos anuales facturables.
    - Estructura de costos comprobables (deducibles) vs. no comprobables (proveedores informales).
    - Tablas impositivas vigentes de ISR e IVA en México.
- **Reto Matemático para el Profesor:** Crear un **Modelo de Simulación de Escenarios Fiscales** que optimice la carga tributaria neta. Debe calcular el "Costo de Formalización" y balancearlo con los beneficios financieros (acceso a mejores tasas de proveedores formales o créditos de la banca de desarrollo).

#### C. Valor de Vida del Cliente () y Dinámica de Clientes ( Mátemático)

- **El Problema:** La PyME gasta recursos persiguiendo nuevos clientes sin entender la tasa de recompra ni el valor financiero que cada cliente aporta a lo largo del tiempo.
- **Variables de Entrada:**
    - Ticket promedio ().
    - Frecuencia de compra mensual ().
    - Tasa de retención de clientes () o tasa de pérdida (_Churn Rate_ = ).
- **Reto Matemático para el Profesor:** Formular el **Valor de Vida del Cliente ()** ajustado por una tasa de descuento financiero que refleje la inflación sectorial actual de México, para optimizar el Costo de Adquisición de Clientes permitido ():  
    Donde  es la tasa de descuento mensualizada.

#### D. El Índice de Vulnerabilidad Neltal () Macroeconómico Completo

- **El Problema:** El ensamble final de las variables micro del negocio con las variables macro del contexto geopolítico mexicano de 2026.
- **Variables de Entrada:**
    - _Microeconómicas:_ Calificaciones normalizadas de , ,  y .
    - _Macroeconómicas:_ Inflación subyacente del Banco de México (INPC), volatilidad cambiaria USD/MXN, y la tasa de referencia monetaria (TIIE).
- **Reto Matemático para el Profesor:** Diseñar el algoritmo de ponderación dinâmica del . El índice no puede ser una simple suma estática. Los pesos () de las variables deben ajustarse dinámicamente mediante una función matemática sensible a la coyuntura macroeconómica. Por ejemplo, en periodos de alta volatilidad cambiaria, el peso de la inflación () en negocios importadores debe incrementarse algorítmicamente de forma automática.  
    Donde  es el vector de variables macroeconómicas del entorno nacional.

## RESUMEN DE ENFOQUES PARA LA SESIÓN ACADÉMICA

Presenta este resumen a tu profesor para enfocar la sesión en el desarrollo de estos tres motores lógicos:

1.  **Para el Nivel Básico:** Queremos desarrollar un **Modelo Probabilístico Conductual** para parametrizar la "Caja Única" y predecir el apego del dueño a los planes de acción usando datos cualitativos e inferencia bayesiana.
2.  **Para el Nivel Intermedio:** Buscamos un motor de **Optimización de Portafolio bajo Restricción Financiera** (Programación Lineal) y un modelo de simulación de tasas de interés compuestas aplicadas a deudas de corto plazo.
3.  **Para el Nivel Avanzado:** Requerimos un **Modelo Gravitacional de Huff** cruzado con bases de datos del INEGI (DENUE) para estimar pérdidas de mercado por competencia territorial, integrado a un sistema de **Suma Ponderada Dinámica** para calcular el IVN bajo condiciones macroeconómicas cambiantes.

eof  
<br/>\### Sugerencias para tu reunión con el profesor:  
<br/>\* \*\*Paso 1:\*\* Entrégale este documento impreso o digital antes de la sesión. Explícale que \*\*Neltal\*\* no busca ser una hoja de Excel automatizada, sino un software con capacidad de predicción y recomendación en tiempo real.  
\* \*\*Paso 2:\*\* Concéntrate en la \*\*Variable INF\*\* y en la de \*\*Caja Única\*\*. Esos son los dos dolores matemáticos más fuertes para la economía popular. Pregúntale: \*"¿Cómo podemos transformar narrativas verbales de un tianguista o taxista en parámetros numéricos estables para meterlos a un algoritmo?"\*  
\* \*\*Paso 3:\*\* Una vez que el profesor te dé sus sugerencias matemáticas, regresa aquí, subimos esas fórmulas al manual de NotebookLM o a nuestras especificaciones y dejamos el motor financiero completamente listo para que el programador empiece a tirar código.  
<br/>¿Cómo ves la estructura de este documento? ¿Hay alguna variable o fenómeno de los negocios reales que te haya tocado ver en el campo y que sientas que debamos agregar a la lista de tareas para el profesor?