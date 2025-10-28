# Parcial-Lenguaje de Programación II
<table>
  <tr>
    <td style="padding-right: 20px;">
      <img src="https://upload.wikimedia.org/wikipedia/commons/a/a9/Unalm_logo.png" width="115" />
    </td>
    <td style="vertical-align: top; font-size: 20px; line-height: 1.0;">
      <strong>Universidad Nacional Agraria La Molina</strong><br><br>
      Facultad de Economía y Planificación<br><br>
      Departamento de Estadística e Informática
    </td>
  </tr>
</table>

**Docente:** Ana Cecilia Vargas Paredes  
📧 *anavargas@lamolina.edu.pe*  
🕒 *Horario de atención:* Martes y jueves, 11:00 – 12:00 h  
🏫 *Oficina:* N.º 13, Facultad de Economía y Planificación  

---

## 🧮 Evaluación Grupal 1 (25%)

**Tema:**  
> Desarrollo de una librería en Python que realice estadísticas básicas utilizando Programación Orientada a Objetos (POO).  
> Incluye clases, herencia y polimorfismo para el análisis de datos cuantitativos y cualitativos.

**Fecha de entrega:** 28 de octubre (23:55 h)  
**Fecha de presentación:** 30 de octubre  
[Presentación 👩‍🏫](https://mar93681-jpg.github.io/Parcial-LP2/)

---

## 👥 Integrantes del grupo

| Integrante   | Aporte   |
|---------------|----------|
| Malvacedo Quiñonez, Jean Franco  | Tarea 1: Arquitectura y Clase Base (25%)  |
| Cruz Cruz, Hilary Penelope       | Tarea 2: Estadísticas Cuantitativas (25%)  |
| Chávez Mendoza, Maria Fernanda   | Tarea 3: Estadísticas Cualitativas (25%)  |
| Mejia Auccapoma, Piero Cesar     | Tarea 4: Integración, Polimorfismo y Pruebas (25%)  |

---

## 📋 Descripción del caso

> **Objetivo:**  
> Desarrollar un paquete o librería en Python que realice **estadísticas básicas** (resúmenes) para datos cuantitativos y cualitativos utilizando principios de **Programación Orientada a Objetos (POO)**.

**Estadísticas consideradas:**
- **Cuantitativas:** media, mediana, desviación estándar, percentiles, etc.  
- **Cualitativas:** moda(s) y tabla de frecuencia.

---

## 🧩 Estructura del proyecto

El proyecto está dividido en tres módulos:

```text
📦 Proyecto_Estadistico/
 ┣ 📜 estadistica_cualitativa.py
 ┣ 📜 estadistica_cuantitativa.py
 ┣ 📜 simular_datos.py
 ┣ 📜 datos_simulados.csv
 ┗ 📜 main.py
```
## Tabla de Contenidos (Archivos del Repositorio)

1. [Base de Estadísticas (EstadisticaBase.py)](libreria/estadisticas_poo/EstadisticaBase.py)
2. [Inicializador (__init__.py)](libreria/estadisticas_poo/__init__.py)
3. [Estadística Cualitativa (estadistica_cualitativa.py)](libreria/estadisticas_poo/estadistica_cualitativa.py)
4. [Estadística Cuantitativa (estadistica_cuantitativa.py)](libreria/estadisticas_poo/estadistica_cuantitativa.py)
6. [Simulador de Datos (simular_datos.py)](libreria/simular_datos.py)
7. [Datos Simulados (datos_simulados.csv)](Data/datos_simulados.csv)
8. [Integración, Polimorfismo y Pruebas (main.py)](libreria/estadisticas_poo/main.py)
9. [Módulo Principal (main.ipynb)](notebooks/main.ipynb)

 ## Diagrama de Clases (UML)
 
 ```mermaid
classDiagram
    direction TB  %% de arriba hacia abajo

    %% Nivel 1: clase abstracta
    class EstadisticaBase {
        <<abstract>>
        +datos
        +cantidad_datos()
        +tipo_datos()
        +resumen()*
    }

    %% Nivel 2: subclases
    class EstadisticaCuantitativa {
        +media()
        +mediana()
        +varianza()
        +percentil()
        +resumen()
    }

    class EstadisticaCualitativa {
        +moda()
        +tabla_frecuencias()
        +resumen()
    }

    %% Nivel 3: clase principal
    class Main {
        +main.py()
    }

    %% Relaciones jerárquicas
    EstadisticaBase <|-- EstadisticaCuantitativa
    EstadisticaBase <|-- EstadisticaCualitativa

    %% Relaciones de uso (de abajo hacia arriba)
    Main ..> EstadisticaCuantitativa : utiliza
    Main ..> EstadisticaCualitativa : utiliza
