<div align="right">
  🌍 <strong>Español</strong> | <a href="README_en.md">English</a>
</div>

# 🚦 Urban Routes: Pruebas de Regresión y Reporte de Errores

![Urban Routes App](https://img.shields.io/badge/Project-Regression_Testing-blue) ![Status](https://img.shields.io/badge/Status-Completed-success) ![Tool](https://img.shields.io/badge/Tool-Jira_/_Google_Sheets-green)

## 📌 Resumen del Proyecto 

*   **Situación:** **Urban Routes** es una aplicación de transporte que crea rutas y calcula la duración y precio del viaje para diferentes tipos de transporte (vehículo personal, taxi, bicicleta, etc.) basándose en puntos "Desde" (A) y "Hasta" (B). El equipo requería garantizar la calidad de la interfaz y la lógica de enrutamiento antes de un pase a producción.
*   **Tarea:** Ejecutar pruebas de regresión detalladas en la interfaz de usuario y la funcionalidad del mapa, identificar discrepancias frente a los requerimientos de diseño y reportar los fallos al equipo de desarrollo.
*   **Acción:** Ejecuté un plan de pruebas exhaustivo cubriendo la interacción con el mapa, campos de dirección, y modos de visualización (Street View, Satélite, Relieve) . Documenté cada ejecución asignando estados precisos y registré informes de error (Bug Reports) con pasos de reproducción, resultados esperados vs. actuales y niveles de severidad.
*   **Resultado:** Se aislaron y reportaron exitosamente múltiples defectos, incluyendo errores **Críticos** que impedían el zoom en direcciones y errores **Menores** de UI. Esto proporcionó al equipo de desarrollo la evidencia exacta necesaria para solucionar los problemas críticos antes de que afectaran la experiencia del usuario final.

---

## 🧪 Muestra Técnica: Diseño de Casos de Prueba

A continuación, presento un ejemplo de cómo estructuro mis casos de prueba, asegurando que cualquier miembro del equipo pueda entender la precondición y los resultados esperados:

| ID | Título del Caso de Prueba | Condición Previa | Pasos | Resultado Esperado | Estado | Bug ID |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **CASO-5** | Se puede seleccionar el campo "Desde" | Abrir la aplicación Urban Routes | 1. Hacer clic en el campo "Desde". | Se selecciona el campo "Desde". El cursor parpadea. El campo de búsqueda está vacío. | ❌ No Aprobada | BR1-01 |

*Nota: Extraído de la suite de pruebas de regresión funcional.*

---

## 🐛 Muestra Técnica: Reporte de Errores (Bug Life Cycle)

Cuando un caso de prueba falla, mi enfoque es proporcionar a los desarrolladores un informe sin ambigüedades. Este es un ejemplo de un defecto crítico encontrado durante la regresión:

| Bug ID | Título | Severidad |
| :--- | :--- | :--- |
| **BR1-02** | El mapa no hace Zoom en la dirección, después de completar el campo "Desde" | 🔴 Crítico |

**Pasos para reproducir:**
1. Abrir la aplicación Urban Routes.
2. Asegurarse de que el campo "Desde" esté vacío.
3. Hacer clic en el campo "Desde".
4. Ingresar una dirección válida (ejemplo: East 2nd Street, 601).

**Resultado Esperado:**
El mapa hace zoom sobre el pin de la dirección seleccionada. La vista debe coincidir con la descripción del diseño.

**Resultado Actual:**
Al ingresar la dirección en el Campo "Desde" la aplicación no realiza la búsqueda ni el acercamiento (zoom) esperado.

---
*🧑‍💻 Perfil Técnico: María Auxiliadora Vélez Mendoza - QA Engineer*
