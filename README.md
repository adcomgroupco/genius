# Genius Bet — Centro documental

Índice e informes de la cuenta Genius Bet El Salvador. `index.html` es el punto de entrada y
enlaza al resto; cada informe vive en su propio archivo y todos comparten el mismo sistema visual.

## Uso local

No requiere instalación ni proceso de compilación.

1. Abre `index.html` directamente en el navegador; o
2. Desde esta carpeta ejecuta `python -m http.server 8000` y visita `http://localhost:8000`.

## Archivos

- `index.html`: centro documental y punto de entrada del proyecto.
- `diagnostico-agosto-2026.html`: diagnóstico de agosto frente al mismo corte de julio; separa
  estructura, eficiencia por campaña, creatividad, contexto deportivo y fricción móvil secundaria.
- `informe-creativo.html`: informe de rendimiento creativo en Meta Ads, para el equipo creativo.
  Las miniaturas de los anuncios van embebidas como data URI, así que la página funciona sin
  conexión y sin carpeta de assets.
- `styles.css`: sistema visual compartido, en Poppins, negro `#050505` / papel `#f4f4f1` y amarillo
  `#ffd400`, heredado de [Raza.do](https://github.com/DanielAdcom98/raza).

### Parámetros de diseño

- Ancho útil máximo de `1340px`, secciones de `52–92px` y tarjetas con radio base de `22px`.
- Títulos de sección limitados a `4.05rem` y portadas a `5.8rem`; el cuerpo se mantiene entre
  `0.8rem` y `1rem` según la función del texto.
- Conclusiones y relaciones causales se presentan como flujos; comparaciones, métricas y acciones
  usan retículas de dos a cuatro columnas antes de apilarse en móvil.
- En pantallas estrechas los flujos pasan a lectura vertical, las listas vuelven a una columna y
  se eliminan los saltos de línea decorativos.

La única dependencia externa es Google Fonts (Poppins). Sin conexión, la página cae al stack de
respaldo declarado en el CSS.

## Para agregar un informe

1. Crea el archivo `nombre-del-informe.html` reutilizando `<link rel="stylesheet" href="styles.css">`
   y la cabecera de `informe-creativo.html` (la marca y el enlace «Índice» apuntan a `index.html`).
2. Añade una `<a class="doc-card">` en el `.doc-grid` de `index.html`, con sus etiquetas, sus tres
   cifras de resumen y el pie.
3. Sube el contador de `.hub-count` en `index.html`.

## Informe creativo Meta Ads

| Sección | Qué responde |
|---|---|
| Cómo leer esto | Por qué captar y hacer jugar se miden distinto |
| Contexto | Evolución mensual del costo por registro y del retorno |
| El hallazgo | Clics frente a registros, tema por tema |
| Captar | Ranking de mensajes por costo por registro + las 6 piezas que funcionaron |
| Hacer jugar | Ranking por retorno + las 5 piezas de mejor rendimiento |
| Replantear | Las 6 piezas a revisar y por qué |
| Formato | Imagen frente a video en cada trabajo |
| Qué comunicar | 6 cosas para hacer, 5 para dejar de hacer |
| Próximo mes | 5 entregas concretas |

### Fuente de cifras

Datos de la API de Meta (Graph v21.0), cuenta `act_2354619758348704` (Genius Bet El Salvador, USD),
a nivel de anuncio. Ventana del 24 de mayo al 20 de agosto de 2026 para piezas y temas, y del
1 de febrero al 20 de agosto de 2026 para la tendencia mensual. Universo de 182 anuncios en
11 campañas y US$52,090 de inversión; solo se muestran piezas con más de US$150 en el período.

«Registro» y «apuesta» son los eventos del píxel `complete_registration` y `purchase`; el retorno
usa el valor que reporta el propio píxel, con la ventana de atribución por defecto de la cuenta.
Son cifras de plataforma, no del sistema del cliente: sirven para comparar piezas entre sí,
no como cierre contable.

## Diagnóstico agosto 2026

Compara el 1–24 de agosto contra el 1–24 de julio de 2026. Usa la API de Meta a nivel de
campaña, anuncio, edad/género y plataforma; incorpora el historial de cambios de la cuenta,
una prueba móvil de Lighthouse ejecutada el 25 de agosto y fuentes externas sobre el calendario
deportivo y las prácticas Performance 5 de Meta.

El informe se concentra en los registros atribuidos, la estructura de campañas y el costo por
registro. La landing se presenta como una oportunidad de soporte, no como la explicación principal
del deterioro.

## Aviso

Contiene inversión, costos por adquisición y retorno de un cliente. **Este repositorio debe
permanecer privado.**
