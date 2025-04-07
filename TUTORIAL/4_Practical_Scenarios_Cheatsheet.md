# 4. Escenarios Prácticos y Hoja de Referencia (Cheat Sheet)

Hemos cubierto la teoría, los operadores y los diversos servicios de Google. Ahora, veamos cómo aplicar estos conocimientos en situaciones prácticas y tengamos a mano una referencia rápida de los comandos clave.

## 💡 Poniéndolo Todo Junto: Ejemplos Prácticos

Estos escenarios son ejemplos simplificados para ilustrar el proceso de pensamiento al combinar herramientas OSINT de Google. Las investigaciones reales suelen ser más complejas e iterativas. **Recuerda siempre actuar con ética y dentro de la legalidad.**

---

### Escenario 1: Investigar una Empresa (Perfil Básico)

* **Objetivo:** Obtener una visión general pública de una empresa ficticia "Innovatech Solutions S.L.".
* **Pasos / Consultas Ejemplo:**

    1.  **Búsqueda General:**
        ```
        "Innovatech Solutions S.L."
        ```
    2.  **Identificar Sitio Web Oficial y Explorarlo:** (Supongamos que es `innovatech-solutions.es`)
        ```
        site:innovatech-solutions.es
        ```
    3.  **Buscar Documentos Públicos (Informes, Presentaciones):**
        ```
        site:innovatech-solutions.es filetype:pdf | filetype:pptx "informe anual" | "presentación corporativa"
        ```
    4.  **Noticias y Menciones en Prensa:**
        ```
        "Innovatech Solutions S.L." noticias | prensa | comunicado
        ```
    5.  **Posibles Empleados (Redes Profesionales):**
        ```
        site:[linkedin.com/in](https://www.google.com/search?q=https://linkedin.com/in) "Innovatech Solutions S.L."
        ```
        *(Nota: Esto solo muestra perfiles públicos indexados que mencionen la empresa).*
    6.  **Ubicación Física (Maps/Street View):** Buscar la dirección registrada en Google Maps. Usar Street View para visualizar la sede u oficinas (si están disponibles y son relevantes).
    7.  **Investigación/Patentes (Scholar/Patents):**
        ```
        intitle:"Innovatech Solutions" site:patents.google.com
        ```

---

### Escenario 2: Verificar la Fuente de una Imagen

* **Objetivo:** Una imagen de un evento inusual circula online. ¿Es real? ¿Cuándo y dónde se originó?
* **Pasos / Consultas Ejemplo:**

    1.  **Búsqueda Inversa:** Ir a Google Images y subir la imagen o pegar su URL.
    2.  **Analizar Resultados:**
        * ¿Aparece la imagen en sitios de noticias fiables?
        * ¿Hay versiones más antiguas de la imagen? (Ordenar por fecha si es posible).
        * ¿El contexto en otras páginas coincide con la historia viral?
    3.  **Identificar Pistas Visuales:** Si la imagen muestra edificios, monumentos o señales reconocibles, intentar localizarlos en Google Maps/Street View.
    4.  **Buscar Metadatos (EXIF):** Descargar la imagen de la fuente más antigua posible y usar un visor EXIF online o local para buscar datos de fecha, hora o GPS (sabiendo que a menudo no estarán).

---

### Escenario 3: Encontrar Informes Gubernamentales sobre un Tema

* **Objetivo:** Localizar informes en PDF sobre "energías renovables" publicados en sitios web gubernamentales españoles (`.es`).
* **Pasos / Consultas Ejemplo:**

    1.  **Búsqueda Específica:**
        ```
        site:gob.es | site:*.ec | site:*.idae.es filetype:pdf "energías renovables" "informe" | "estudio"
        ```
        *(Ajusta los dominios `.es` relevantes según el área de gobierno).*
    2.  **Ampliar Tipos de Archivo:**
        ```
        site:gob.es filetype:pptx | filetype:docx "presentación" "energías renovables"
        ```
    3.  **Refinar por Año (si es necesario, con comillas):**
        ```
        site:gob.es filetype:pdf "energías renovables" "informe" "2024"
        ```

---

## 📌 Hoja de Referencia Rápida (Cheat Sheet) de Operadores

Aquí tienes un recordatorio rápido de los operadores más utilizados:

| Operador                        | Descripción                                      | Ejemplo                                             |
| :------------------------------ | :----------------------------------------------- | :-------------------------------------------------- |
| `site:dominio.com`              | Limita la búsqueda a ese sitio web.              | `informe site:ejemplo.com`                          |
| `filetype:ext` / `ext:`         | Busca tipos de archivo específicos (pdf, xlsx...). | `manual filetype:pdf`                               |
| `"frase exacta"`                | Busca la secuencia literal de palabras.          | `"inteligencia de fuentes abiertas"`                |
| `-término`                      | Excluye resultados que contengan el término.     | `jaguar velocidad -coche`                           |
| `*`                             | Comodín para palabras en una frase exacta.       | `"el * más rápido"`                                 |
| `OR` / `|`                      | Busca resultados con término A **o** término B.    | `portátil OR laptop`                                |
| `intitle:término`               | Busca el término en el título de la página.      | `intitle:"panel de control"`                        |
| `inurl:término`                 | Busca el término en la URL.                      | `inurl:login`                                       |
| `intext:término`                | Busca el término en el cuerpo del texto.         | `intext:"confidencial"`                             |
| `related:dominio.com`           | Encuentra sitios web similares.                  | `related:wikipedia.org`                             |
| `cache:url`                     | Muestra la versión cacheada por Google.          | `cache:ejemplo.com/pagina`                          |
| `terminoA terminoB`             | Busca resultados con **ambos** términos (AND implícito). | `seguridad informática`                             |
| `allintitle:/allinurl:/allintext:` | Todas las palabras siguientes deben estar en el título/URL/texto. | `allintitle:admin login panel` |


## ✅ Consejos Finales

* **Práctica, Práctica, Práctica:** La mejor forma de dominar OSINT con Google es experimentar con diferentes combinaciones de operadores y servicios.
* **Combina Herramientas:** Google es potente, pero es solo una pieza del puzzle OSINT. Combínala con otras herramientas y técnicas según tus necesidades.
* **Mantente Actualizado:** Google cambia sus algoritmos y funcionalidades. Lo que funciona hoy puede cambiar mañana. Sigue aprendiendo.
* **¡SÉ ÉTICO!** No podemos enfatizarlo lo suficiente. Usa tus habilidades de forma responsable y legal.

##🏁 Conclusión del Tutorial

¡Felicidades! Has completado este recorrido por el uso de Google para OSINT. Esperamos que esta guía te haya proporcionado una base sólida para encontrar y analizar información en fuentes abiertas de manera efectiva y ética. ¡Ahora te toca a ti ponerlo en práctica!