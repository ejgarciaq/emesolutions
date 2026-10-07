# AGENTS.md — Estándares de Desarrollo & Revisión para Emesolutions

Este archivo define las reglas de calidad, buenas prácticas y arquitectura de diseño para la landing page de consultoría tecnológica, ciberseguridad, auditoría y desarrollo Enterprise de **emesolutions**.

---

## 1. Guía de Identidad & Paleta Corporativa

Cualquier componente UI, hoja de estilos (CSS/Tailwind) o propuesta visual debe respetar estrictamente la siguiente especificación de color:

*   **Azul Marino Profundo (Color Primario / Dominante):**
    *   **HEX:** `#0A192F` | **RGB:** `(10, 25, 47)`
    *   **Uso:** Fondos principales, héroe (hero section), barra de navegación, encabezados principales, footers y pies de documentos.
    *   **Objetivo:** Transmitir estabilidad, sobriedad y seguridad de la información.
*   **Azul Cyan / Tech Blue (Acento Tecnológico):**
    *   **HEX:** `#00B4D8` | **RGB:** `(0, 180, 216)`
    *   **Uso:** Botones de acción principales (CTA), isotipos, estados activos, enlaces hover, bordes de enfoque y resaltados de propuesta de valor.
*   **Gris Grafito Neutro (Texto Principal):**
    *   **HEX:** `#2D3748` | **RGB:** `(45, 55, 72)`
    *   **Uso:** Cuerpo de texto, descripciones, manuales, documentación técnica y términos contractuales.
*   **Blanco Puro / Gris Claro (Fondo de Interfaz Neutro):**
    *   **HEX:** `#F8FAFC` | **RGB:** `(248, 250, 252)`
    *   **Uso:** Fondos de secciones claras, tarjetas (cards) de servicios, contenedores de contenido y formularios.

---

## 2. Reglas de Estructura Visual y Copywriting Enterprise

1.  **Propuesta de Valor Clara en Hero:** El primer impacto debe transmitir solvencia técnica, protección de datos y servicios Enterprise en menos de 3 segundos de lectura.
2.  **Jerarquía de Llamados a la Acción (CTA):**
    *   El CTA primario debe usar la tonalidad `#00B4D8` con alto contraste y texto orientado a conversión B2B (*p. ej., "Agendar Auditoría Inicial"* o *"Solicitar Consultoría Técnica"*).
    *   Solo se permite un CTA primario visible por sección.
3.  **Secciones Indispensables de la Landing Page:**
    *   **Hero Section:** Título claro, propuesta de valor, CTA principal y badges de confianza.
    *   **Pilares de Servicio:** Ciberseguridad & Hardening, Auditoría IT & Cumplimiento, Desarrollo de Software Enterprise, e Infraestructura Cloud/On-Premise.
    *   **Sección de Confianza y Garantía:** Estándares de seguridad de datos, metodología de trabajo (SDD/ODD) e indicadores cuantitativos.
    *   **Formulario de Contacto B2B:** Validación estricta en lado de cliente y servidor, con campos estructurados para empresa, correo corporativo y necesidad técnica.
    *   **Footer Corporativo:** Enlaces legales, datos de facturación/contacto y derechos reservados.

---

## 3. Calidad de Código y Estándares Técnicos

### Frontend & Marcado
*   **HTML5 Semántico Obligatorio:** Utilizar etiquetas semánticas (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`) para mejorar indexación SEO y lectura por agentes de asistencia.
*   **Accesibilidad (WCAG 2.1 AA):**
    *   Relación de contraste suficiente entre el texto (`#2D3748` o blanco) y sus respectivos fondos (`#0A192F` o `#F8FAFC`).
    *   Todos los elementos interactivos deben contar con etiquetas `aria-label` o `alt` explícitas.
*   **Rendimiento y Optimización:**
    *   Imágenes y assets optimizados en formatos modernos (WebP/SVG).
    *   Cero código muerto o librerías pesadas no utilizadas en producción.
    *   Carga diferida (`loading="lazy"`) para recursos pesados fuera del primer pantallazo.

### Seguridad y Hardening en Landing
*   No exponer variables de entorno sensibles, llaves privadas ni endpoints administrativos en scripts del lado del cliente.
*   Sanitización estricta de entradas en todos los campos de formularios para prevenir inyecciones de código (XSS).
*   Configuración previa para cabeceras de seguridad web (`Content-Security-Policy`, `X-Frame-Options`).

---

## 4. Criterios de Revisión para GGA (Gentleman Guardian Angel)

Durante la ejecución de `gga run` o en la validación del hook `pre-commit`, el código será rechazado si:

*   Se introducen colores fuera de la paleta corporativa definida.
*   Existen instrucciones `console.log`, alertas de prueba o código de depuración temporal.
*   Se detectan etiquetas `<img>` sin atributo `alt` o botones sin texto descriptivo.
*   El código presenta errores de sintaxis CSS/HTML o enlaces rotos en la navegación.