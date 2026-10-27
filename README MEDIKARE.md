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

