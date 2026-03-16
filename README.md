# domaindall

domaindall es una herramienta de análisis de dominios orientada a la investigación OSINT, la evaluación de seguridad y la visibilidad técnica de la infraestructura asociada a un dominio.

A partir de un dominio, la plataforma recopila, correlaciona y presenta información clave sobre su resolución, trazabilidad, autenticación de correo, exposición externa y posibles vulnerabilidades, ofreciendo una visión unificada del riesgo técnico y operativo.

## Qué hace domaindall

domaindall permite introducir cualquier dominio y obtener un análisis estructurado en varios apartados:

### 1. Análisis OSINT del dominio

Este módulo realiza una inspección técnica y de contexto sobre el dominio analizado, mostrando datos como:

- Número total de saltos detectados
- Jurisdicciones por las que podría pasar el tráfico
- Servidores DNS implicados en la resolución
- Latencia total observada
- Destino final alcanzado
- Entidad asociada y posible jurisdicción legal

Además, domaindall genera una **ruta geopolítica estimada** en la que se representan los saltos detectados y una hipótesis razonable del recorrido que podrían seguir los datos. Esta visualización se apoya en un mapa integrado con infraestructura de cableado submarino y correlación de latencia, permitiendo inferir por qué regiones o enlaces internacionales podría transitar el tráfico en determinados escenarios.

### 2. Resolución DNS y root servers

La resolución DNS se apoya en la jerarquía del sistema DNS, incluyendo la participación de root servers cuando corresponde dentro del proceso de resolución. domaindall muestra esta capa como parte del análisis para ayudar a entender el punto inicial de la consulta, la infraestructura implicada y la trazabilidad técnica del dominio desde su resolución base hasta el destino final.

### 3. Análisis DMARC, SPF y DKIM

domaindall incorpora un módulo específico para evaluar la seguridad del correo asociado al dominio mediante el análisis de:

- DMARC
- SPF
- DKIM

El sistema recopila la configuración publicada por el dominio, la segmenta y explica de forma comprensible qué tiene implementado y para qué sirve cada elemento. Entre otros aspectos, se revisan:

- Política DMARC
- Registros `rua`
- Registros `ruf`
- Modo de alineación
- Aplicación de políticas
- Selectores DKIM más comunes
- Configuración SPF y su alcance

A partir de esta información, domaindall genera una valoración porcentual y un **score global de seguridad**, facilitando una interpretación rápida del nivel de protección actual del dominio frente a suplantación, spoofing y malas configuraciones de correo.

### 4. Vulnerabilidades asociadas al dominio

Otro de los apartados principales de domaindall es el análisis de vulnerabilidades relacionadas con el dominio y su infraestructura expuesta, utilizando como referencia fuentes como:

- CVE
- INCIBE

La información recopilada se clasifica por severidad en:

- Crítico
- Alto
- Medio
- Bajo

Para cada vulnerabilidad detectada o asociada, la herramienta presenta un resumen técnico que incluye:

- Descripción breve
- Puntuación CVSS
- Explotabilidad
- Impacto
- Productos afectados
- Estado del parche o mitigación
- Fuentes consultadas
- Referencias adicionales

El objetivo es ofrecer contexto útil y accionable, no solo enumerar vulnerabilidades.

### 5. Dominios y subdominios expuestos

domaindall también analiza la superficie de exposición externa de la entidad vinculada al dominio principal, identificando posibles dominios o subdominios relacionados que estén públicamente expuestos.

Cada activo detectado se clasifica por criticidad:

- Crítico
- Alto
- Medio
- Bajo

En cada resultado se muestran además datos asociados al certificado digital, incluyendo:

- Emisor del certificado
- Fecha de validez desde
- Fecha de validez hasta

Esto permite detectar activos olvidados, infraestructuras secundarias mal mantenidas, entornos heredados o puntos de exposición con potencial riesgo operativo.

## Objetivo del proyecto

El objetivo de domaindall es centralizar en una sola herramienta distintas capacidades de análisis que normalmente se encuentran dispersas entre soluciones OSINT, verificadores DNS, validadores DMARC y fuentes de inteligencia de vulnerabilidades.

La plataforma está pensada para investigadores, analistas de seguridad, equipos defensivos, auditores técnicos y cualquier perfil que necesite comprender mejor la huella digital, la exposición y el nivel de madurez de seguridad de un dominio.

## Enfoque

domaindall no se limita a mostrar datos en bruto. Su enfoque es correlacionar información técnica, contextualizarla y clasificarla para facilitar la toma de decisiones.

El resultado es una visión más completa del dominio analizado, combinando:

- Trazabilidad de red
- Contexto geopolítico estimado
- Seguridad del correo
- Inteligencia de vulnerabilidades
- Exposición de activos relacionados

## Aviso

La información mostrada por domaindall se basa en fuentes públicas, correlaciones técnicas e inferencias razonables a partir de la resolución, latencia, registros y activos detectados. Algunos apartados, como la ruta geopolítica estimada del tráfico, deben entenderse como una aproximación analítica y no como una representación exacta del recorrido real de los datos en todos los casos.
