# 📂 Documentación Técnica de Pruebas: Urban Routes

Este documento detalla el alcance técnico, la estrategia y las evidencias del ciclo de pruebas de regresión ejecutado para la aplicación Urban Routes.

## 🧠 Contexto del Proyecto: ¿Qué es Urban Routes?
Urban Routes es una aplicación web de transporte y movilidad. Su funcionalidad principal consiste en crear rutas y calcular la duración y el precio del viaje basándose en dos puntos: origen ("Desde" / Punto A) y destino ("Hasta" / Punto B) [1, 2]. La aplicación cuenta con una interfaz que permite al usuario seleccionar entre tres modos de viaje ("Óptimo", "Flash" y "Personal") y varios tipos de transporte (automóvil, a pie, taxi, bicicleta, scooter, etc.) [1].

## 🎯 Alcance de las Pruebas (¿Qué estábamos probando?)
El objetivo de este sprint fue ejecutar **pruebas de regresión** para garantizar que la interfaz de usuario y la lógica del mapa funcionaran correctamente frente a interacciones complejas [1]. El alcance de mis pruebas incluyó:

1. **Interacción con el Mapa:** Validación de desplazamientos, funcionalidad de Zoom (acercar/alejar), y renderizado de objetos 3D y lugares de interés [3-6].
2. **Modos de Visualización:** Comprobación de las transiciones entre la vista estándar, el modo Satélite, el modo Relieve y la activación/desactivación del modo Street View [7-10].
3. **Campos de Entrada (Inputs):** Pruebas exhaustivas en los campos "Desde" y "Hasta", validando la selección, inserción de datos, limpieza de campos (botón "X") y la aparición correcta de los pines de dirección en el mapa [4, 11, 12].
4. **Comportamiento de la UI:** Verificación del modo de pantalla completa y la correcta visualización de las pestañas e interfaz de la aplicación durante este estado [13].

---

## 🧪 Casos de Prueba (Muestra)

A continuación, se presenta un extracto de los casos de prueba diseñados para la validación de los campos de entrada, demostrando la estructura utilizada para precondiciones y resultados esperados.

| ID | Título del Caso de Prueba | Condición Previa | Pasos | Resultado Esperado | Estado | Bug ID |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **CASO-5** | Se puede seleccionar el campo "Desde" | Abrir la aplicación Urban Routes | 1. Hacer clic en el campo "Desde". | Se selecciona el campo "Desde". El cursor parpadea. El campo de búsqueda está vacío [11]. | ❌ No Aprobada | BR1-01 |
| **CASO-9** | La dirección se elimina después de borrar el campo "Desde" | Abrir la aplicación Urban Routes. El campo "Desde" debe estar lleno | 1. Hacer clic en la "X" del campo "Desde". | El campo se vacía. La dirección ingresada anteriormente se elimina del campo [12]. | ✅ Aprobada | N/A |

---

## 🐛 Reporte de Errores (Muestra de Bug Life Cycle)

Durante la regresión, identifiqué fallos que afectaban la experiencia del usuario. El siguiente es un ejemplo de cómo aislo y documento un defecto crítico de lógica en el mapa:

| Bug ID | Título | Severidad |
| :--- | :--- | :--- |
| **BR1-02** | El mapa no hace Zoom en la dirección, después de completar el campo "Desde" [14] | 🔴 Crítico [15] |

**Pasos para reproducir:**
1. Abrir la aplicación Urban Routes [16].
2. Asegurarse de que el campo "Desde" esté vacío [16].
3. Hacer clic en el campo "Desde" [16].
4. Ingresar una dirección válida (ejemplo: East 2nd Street, 601) [16].

**Resultado Esperado:**
El mapa hace zoom sobre el pin de la dirección seleccionada. La vista coincide con la descripción del diseño [15].

**Resultado Actual:**
Al ingresar la dirección en el Campo "Desde" no realiza la búsqueda ni el acercamiento esperado [17].

---
*Documentación estructurada por María Auxiliadora Vélez Mendoza.*