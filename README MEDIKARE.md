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

Requerimientos levantados por el equipo y registrados como *Issues* en GitHub (numeración `#` = número del issue).

### 2.1 Requerimientos funcionales (RF)

| ID | Requerimiento | Issue |
|----|---------------|-------|
| RF-01 | Registrar cliente (nombre, cédula, síntomas, dirección de residencia) | #1 |
| RF-02 | Tipo de plan (siglas PB o PP) | #2 |
| RF-03 | Otros usuarios (número entero) | #3 |
| RF-04 | Valor mensual (tipo de plan × otros usuarios) | #4 |
| RF-05 | Respaldo TXT | #5 |
| RF-06 | Descuento del 12,5 % si el síntoma es gripa o alergia | #6 |
| RF-07 | Historial de clientes | #7 |
| RF-08 | Cierre de sesión | #8 |
| RF-09 | Ciclo continuo | #9 |
| RF-10 | Protocolo de parada inmediata | #10 |

### 2.2 Requerimientos no funcionales (RNF)

| ID | Requerimiento | Issue |
|----|---------------|-------|
| RNF-01 | Guardado seguro en la computadora | #11 |
| RNF-02 | Sin problemas por usar mayúsculas o minúsculas | #12 |
| RNF-03 | Control de pasos y seguridad de los datos | #13 |
| RNF-04 | Funcionalidad en cualquier entorno | #14 |

### 2.3 Reglas de dominio (RD)

| ID | Regla | Issue |
|----|-------|-------|
| RD-01 | Respetar los precios fijos de la empresa: plan básico **275.325 COP** y plan premium **325.650 COP** | #15 |
| RD-02 | Guardar el historial sin borrar a los pacientes anteriores | #16 |
| RD-03 | Proteger la privacidad y los datos personales de los clientes | #17 |

### 2.4 Trazabilidad con el programa

| Requerimiento | Dónde se cumple en `MediKare.java` |
|---------------|------------------------------------|
| RF-01 a RF-04 | Opciones 1 a 4 del menú |
| RF-05 | Opción 5, método `respaldarTXT()` |
| RF-06 | Opción 6, método `aplicarDescuento()` |
| RF-07 | Opción 7, método `visualizar()` |
| RF-08 | Opción 8 (salir) |
| RF-09 | Ciclo `do-while` del menú |
| RF-10 | La palabra "medicamento" cierra la factura del cliente |
| RNF-02 | `toUpperCase()` y `equalsIgnoreCase()` al leer el plan y la palabra de parada |
| RD-01 | Constantes `PLAN_BASICO` y `PLAN_PREMIUM` |
| RD-02 | Lista `clientes`, que conserva a todos los clientes de la sesión |

### 2.5 Supuestos

- "Otros usuarios" es el número de personas cubiertas por el plan (mínimo 1).
- El descuento se calcula sobre el valor mensual ya calculado.
- Los síntomas se ingresan uno por uno; "medicamento" cierra la factura y la opción 1 siguiente abre un cliente nuevo.

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

- [x] Requerimientos (este README y los Issues de GitHub)
- [x] Backlog e historias de usuario (`BACKLOG.md`)
- [x] Código comentado (`MediKare.java`)
- [x] Nombre, logo, misión y visión
- [ ] Video explicativo (grabar siguiendo el guion)
