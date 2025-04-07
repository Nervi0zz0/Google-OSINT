# 2. Dominando los Operadores de Búsqueda de Google (Google Dorking)

Los operadores de búsqueda de Google (a menudo llamados "dorks") son comandos especiales que puedes añadir a tus consultas para filtrar y refinar los resultados de manera increíblemente precisa. Dominarlos es esencial para OSINT efectivo con Google.

## Operadores Fundamentales

Estos son los pilares básicos que usarás constantemente.

### `site:`
* **Qué hace:** Limita la búsqueda a un sitio web o dominio específico.
* **Sintaxis:** `termino site:ejemplo.com`
* **Ejemplos:**
    * `informe anual site:empresa-ejemplo.com` (Busca "informe anual" solo en ese dominio)
    * `contacto site:blog.ejemplo.com` (Busca en un subdominio específico)
    * `site:gob.es` (Explora páginas indexadas de ese dominio)

### `filetype:` o `ext:`
* **Qué hace:** Busca tipos de archivo específicos.
* **Sintaxis:** `termino filetype:pdf` o `termino ext:pdf`
* **Tipos comunes:** `pdf`, `docx`, `xlsx`, `pptx`, `txt`, `csv`, `log`, `sql`, `bak`, `config`, `xml`, `json`.
* **Ejemplos:**
    * `presupuesto filetype:xlsx` (Busca hojas de cálculo con la palabra "presupuesto")
    * `manual usuario filetype:pdf site:producto-ejemplo.com` (Busca manuales PDF en un sitio específico)

### `""` (Comillas Exactas)
* **Qué hace:** Busca una frase exacta.
* **Sintaxis:** `"frase exacta"`
* **Ejemplo:** `"informe de inteligencia de fuentes abiertas"` (Busca esa secuencia exacta de palabras)

### `*` (Comodín)
* **Qué hace:** Actúa como un marcador de posición para una o más palabras desconocidas dentro de una frase exacta.
* **Sintaxis:** `"frase con * comodín"`
* **Ejemplo:** `"el * más grande del mundo"`

### `-` (Exclusión)
* **Qué hace:** Excluye resultados que contengan un término específico.
* **Sintaxis:** `termino -palabra_a_excluir`
* **Ejemplo:** `jaguar velocidad -coche` (Busca sobre el animal jaguar, excluyendo resultados sobre el coche)

### `OR` o `|` (Alternativa)
* **Qué hace:** Busca resultados que contengan el término A *o* el término B.
* **Sintaxis:** `terminoA OR terminoB` o `terminoA | terminoB`
* **Ejemplo:** `elecciones presidenciales | votaciones generales`

### `AND` (Implícito)
* **Nota:** Generalmente, Google trata los espacios entre palabras como un operador `AND` (buscar resultados que contengan todas las palabras), por lo que raramente necesitas escribir `AND` explícitamente.

## Operadores de Ubicación de Términos

Estos operadores buscan tus términos en partes específicas de una página web.

### `intitle:`
* **Qué hace:** Busca el término especificado solo en el título de la página web (lo que ves en la pestaña del navegador).
* **Sintaxis:** `intitle:termino`
* **Ejemplo:** `intitle:"panel de administración"`

### `inurl:`
* **Qué hace:** Busca el término especificado dentro de la URL de la página.
* **Sintaxis:** `inurl:termino`
* **Ejemplo:** `inurl:login` o `inurl:admin.php`

### `intext:`
* **Qué hace:** Busca el término especificado solo en el cuerpo principal del texto de la página (ignora título, URL, enlaces).
* **Sintaxis:** `intext:termino`
* **Ejemplo:** `intext:"número de seguridad social"` (¡Usar con ética!)

### Variantes `allintitle:`, `allinurl:`, `allintext:`
* **Qué hacen:** Requieren que *todas* las palabras siguientes aparezcan en el título, URL o texto, respectivamente.
* **Ejemplo:** `allintitle:panel administración login`

## Operadores Relacionados y de Caché

### `related:`
* **Qué hace:** Encuentra sitios web similares o relacionados a una URL dada.
* **Sintaxis:** `related:sitioejemplo.com`
* **Ejemplo:** `related:nytimes.com` (Encuentra otros sitios de noticias importantes)

### `cache:`
* **Qué hace:** Muestra la versión de una página web tal como Google la guardó (cacheó) la última vez que la visitó. Útil si la página original está caída o ha cambiado.
* **Sintaxis:** `cache:sitioejemplo.com/pagina`
* **Ejemplo:** `cache:wikipedia.org/wiki/OSINT`

## Combinando Operadores: El Arte del Google Dorking

La verdadera potencia surge al combinar múltiples operadores en una sola consulta. Esto te permite crear filtros extremadamente específicos.

* **Ejemplo 1: Encontrar paneles de login**
    ```
    site:[empresa-objetivo.com](https://www.google.com/search?q=empresa-objetivo.com) intitle:"login" | intitle:"sign in" | inurl:login | inurl:admin
    ```
* **Ejemplo 2: Buscar documentos específicos con términos clave**
    ```
    site:gobierno-ejemplo.org filetype:pdf "confidencial" | "interno"
    ```
* **Ejemplo 3: Encontrar listados de directorios abiertos (potencialmente inseguros)**
    ```
    intitle:"index of /" "parent directory"
    ```
    ```
    intitle:"index of /" + "server at"
    ```
* **Ejemplo 4: Buscar archivos de configuración o backups**
    ```
    filetype:sql | filetype:bak | filetype:config "password" | "contraseña" | "db_user"
    ```

* **¡Sé creativo!** Experimenta combinando `site:`, `filetype:`, `intitle:`, `inurl:` y términos exactos para afinar tus búsquedas OSINT.

## Buenas Prácticas y Advertencias

* **Empieza Simple:** No uses demasiados operadores al principio. Empieza con uno o dos y añade más gradualmente si es necesario.
* **Google te Observa:** Consultas muy complejas o muy rápidas pueden activar CAPTCHAs o bloqueos temporales. Sé paciente.
* **Ética Siempre:** Recuerda la sección de ética. Usa estos operadores para fines legítimos, educativos o defensivos. **No** uses dorks para buscar activamente vulnerabilidades en sistemas ajenos sin permiso.
* **ToS:** Evita herramientas que automaticen masivamente las búsquedas de dorks, ya que pueden violar los Términos de Servicio de Google.

---
*En el siguiente módulo, exploraremos otros servicios de Google más allá del buscador principal.*