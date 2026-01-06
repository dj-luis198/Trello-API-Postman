[![Run API Tests and Publish Dashboard](https://github.com/dj-luis198/Trello-API-Postman/actions/workflows/api-tests.yml/badge.svg)](https://github.com/dj-luis198/Trello-API-Postman/actions/workflows/api-tests.yml)

# Trello API Testing with Postman CLI 🚀

Este proyecto contiene pruebas automatizadas para la API de Trello utilizando **Postman CLI** y **GitHub Actions**.  
El objetivo es validar el flujo de trabajo de tarjetas en un tablero Kanban con tres listas: **TO DO**, **IN PROGRESS** y **DONE**.

🔗 **Reporte en vivo:** [Dashboard de pruebas](https://dj-luis198.github.io/Trello-API-Postman/)

---

## 📌 Descripción del flujo de pruebas

1. **Creación de tarjetas**  
   - Se crean nuevas cards en la lista **TO DO**.

2. **Movimiento de tarjetas**  
   - Las cards se mueven progresivamente a **IN PROGRESS** y luego a **DONE**.

3. **Validación de estados**  
   - Se verifican las respuestas de la API (status codes, payloads, tiempos de respuesta).

4. **Limpieza final**  
   - Una vez completadas las pruebas, los tableros se limpian para dejar el entorno listo para la próxima ejecución.

---

## ⚙️ Tecnologías utilizadas

- [Postman CLI](https://learning.postman.com/docs/postman-cli/command-line-interface/)  
- [GitHub Actions](https://docs.github.com/actions)  
- [GitHub Pages](https://pages.github.com/)  
- Trello API

---

## ▶️ Cómo correr las pruebas

### 1. Requisitos previos
- Tener una cuenta en Trello.  
- Obtener tu **API Key** y **Token** desde [Trello Developer API Keys](https://trello.com/app-key).  
- Exportar tu colección y environment desde Postman (`coleccion.json`, `environment.json`).  

### 2. Configuración en GitHub
- Subir los archivos `coleccion.json` y `environment.json` al repo (ej. carpeta `postman/`).  
- Configurar los secretos en el repositorio:  
  - `KEY` → tu API Key de Trello  
  - `TOKEN` → tu Token de Trello  

### 3. Ejecución automática
Cada vez que haces **push** a la rama `main`, GitHub Actions:
1. Instala Postman CLI.  
2. Corre la colección con tus credenciales.  
3. Genera un reporte HTML (`reporte.html`).  
4. Publica el reporte en la rama `gh-pages`.  

👉 El resultado queda disponible en:  
[https://dj-luis198.github.io/Trello-API-Postman/](https://dj-luis198.github.io/Trello-API-Postman/)

### 4. Ejecución manual
- Ve a la pestaña **Actions** en tu repo.  
- Selecciona el workflow **Run API Tests and Publish Dashboard**.  
- Haz clic en **Run workflow** para dispararlo manualmente.

---

## 📊 Resultados

El reporte HTML incluye:
- Resumen de requests ejecutadas.  
- Status codes y tiempos de respuesta.  
- Tests pasados y fallidos.

---

## 📌 Notas importantes

- Los secretos (`KEY`, `TOKEN`) **no se publican** en el reporte gracias a la sanitización previa.  
- El tablero se limpia al final de cada ejecución para mantener un entorno reproducible.  
- Puedes descargar el reporte como artefacto desde la pestaña **Actions** además de verlo
