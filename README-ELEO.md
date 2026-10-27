<p align="center">
  <img src="logo.svg" alt="Logo MediKare" width="420">
</p>

<h1 align="center">MediKare</h1>
<p align="center"><em>Cuidamos de ti, donde estés.</em></p>

<p align="center">Sistema en Java para una empresa de servicio médico en casa con planes preventivos – Caso B (Segundo corte)</p>

---

## Misión

En MediKare llevamos atención médica preventiva y oportuna hasta el hogar de cada familia. Ofrecemos planes accesibles, un equipo de profesionales calificados y un trato humano, apoyados en tecnología que hace más simple registrar, atender y facturar.

## Visión

Para 2030, MediKare será la plataforma de servicio médico domiciliario de referencia en Colombia, reconocida por la calidad de su atención, la innovación de su sistema y la confianza de las familias que cuida.

## Valores

Cuidado humano, confianza, responsabilidad, innovación y compromiso con la prevención.

---

## 1. Identidad de la empresa (generada con apoyo de IA)

**Nombre:** MediKare
**Eslogan:** *Cuidamos de ti, donde estés.*
**Logo:** un escudo azul-turquesa con un corazón y una línea de pulso cardíaco, que representa protección y cuidado de la salud (archivo `logo.svg`).

## 2. Levantamiento de requerimientos

### 2.1 Requerimientos funcionales

| ID | Requerimiento |
|----|---------------|
| RF-01 | El sistema debe permitir registrar un cliente con nombre, cédula, síntomas y dirección de residencia. |
| RF-02 | El sistema debe permitir elegir el tipo de plan con las siglas **PB** (básico) o **PP** (premium). |
| RF-03 | El sistema debe registrar la cantidad de otros usuarios cubiertos (número entero ≥ 1). |
| RF-04 | El sistema debe calcular el valor mensual: `valor = precio del plan × otros usuarios`. |
| RF-05 | El sistema debe guardar un respaldo de los datos en un archivo TXT. |
| RF-06 | El sistema debe aplicar un descuento del 12,5 % en ambos planes si el síntoma es gripa o alergia. |
| RF-07 | El sistema debe mostrar la información de los clientes registrados. |
| RF-08 | El sistema debe tener la opción de salir. |
| RF-09 | El sistema debe ser continuo (menú repetitivo) para registrar varios usuarios. |
| RF-10 | La factura de un cliente termina cuando el médico escribe la palabra "medicamento". |

### 2.2 Requerimientos no funcionales

| ID | Requerimiento |
|----|---------------|
| RNF-01 | Desarrollado en Java, ejecutable por consola. |
| RNF-02 | Validar entradas (plan PB/PP, enteros) sin que el programa se detenga por errores. |
| RNF-03 | Código comentado y legible. |
| RNF-04 | Los valores se muestran en pesos colombianos (COP). |

### 2.3 Reglas de negocio

- Plan básico (PB): **275.325 COP**
- Plan premium (PP): **325.650 COP**
- Descuento: **12,5 %** si los síntomas incluyen gripa o alergia.
- Palabra de cierre de factura: **medicamento**.

### 2.4 Supuestos

- "Otros usuarios" se interpreta como el número de personas cubiertas por el plan (mínimo 1).
- El descuento se calcula sobre el valor mensual ya calculado.
- Los síntomas se ingresan uno por uno; "medicamento" cierra la factura y abre un cliente nuevo.

## 3. Cómo ejecutar

```bash
javac MediKare.java
java MediKare
```

Ejemplo de uso: opción 1 (registrar datos y síntomas; cerrar con "medicamento") → 2 (PB) → 3 (2 personas) → 4 (valor) → 6 (descuento) → 7 (visualizar) → 5 (respaldo). Para atender otro cliente se vuelve a elegir la opción 1, que abre un registro nuevo.

## 4. Guion para el video explicativo (3 a 4 minutos)

1. **Presentación (20 s):** nombre del equipo, caso B y MediKare.
2. **Identidad (30 s):** mostrar logo, misión y visión.
3. **Requerimientos y backlog (40 s):** mostrar el repositorio de GitHub, README y BACKLOG.
4. **Código (60 s):** recorrer las constantes, la clase `Cliente`, el menú con `switch` y el ciclo `do-while`.
5. **Demostración (60 s):** registrar un cliente con gripa, elegir PB, 2 personas, calcular, aplicar descuento, visualizar, generar el TXT y cerrar con "medicamento".
6. **Cierre (10 s):** conclusiones y agradecimientos.

## 5. Entregables

- [x] Requerimientos (este README)
- [x] Backlog e historias de usuario (`BACKLOG.md`)
- [x] Código comentado (`MediKare.java`)
- [x] Nombre, logo, misión y visión
- [ ] Video explicativo (grabar siguiendo el guion)
