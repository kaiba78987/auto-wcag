---
rule_id: SC2-1-1-keyboard-operation-alternative-to-mouse_event
name: Operatividad por teclado como alternativa a eventos del mouse
test_mode: semi-automatic
environment: Web Browser

success_criterion:
- 2.1.1 # Keyboard  (level A)

authors:
- José Hilera, Francisco Estrada, Cristian Timbi
---

## Description

Este test chequea si la funcionalidad del contenido es operable a travez del teclado


## Background

- [G90: Providing keyboard-triggered event handlers](http://www.w3.org/TR/WCAG-TECHS/G90)
- [F59: Failure of Success Criterion 4.1.2 due to using script to make div or span a user interface control in HTML without providing a role for the control](https://www.w3.org/TR/2016/NOTE-WCAG20-TECHS-20161007/F59.html)
- [F42: Failure of Success Criteria 1.3.1, 2.1.1, 2.1.3, or 4.1.2 when emulating links](https://www.w3.org/TR/2016/NOTE-WCAG20-TECHS-20161007/F42)
- [F54: Failure of Success Criterion 2.1.1 due to using only pointing-device-specific event handlers (including gesture) for a function](http://www.w3.org/TR/2016/NOTE-WCAG20-TECHS-20161007/F54)
- [F55: Failure of Success Criteria 2.1.1, 2.4.7, and 3.2.1 due to using script to remove focus when focus is received](http://www.w3.org/TR/2016/NOTE-WCAG20-TECHS-20161007/F55)
- [Accessible Rich Internet Applications (WAI-ARIA) Version 1.0](http://www.w3.org/TR/wai-aria/)

## Assumptions

- .

## Test procedure

### Selector

Select all elements that match the following CSS selector:

    *[ondblclick],
    *[onmousedown],
    *[onmouseout],
    *[onmouseover],
    *[onmouseup],
    *[onmousemove]

### Step 1

Chequear si la funcionalidad proporcionada por el elemento seleccionado esta disponible a travéz del teclado.

Si sí, return [step1-pass](#step1-pass)

casocontrario, retorna [step1-fail](#step1-fail)

## Outcome

The resulting assertion is as follows,

| Property | Value
|----------|----------
| type     | Assertion
| test     | auto-wcag:{{ page.rule_id }}
| subject  | *the selected element*
| mode     | auto-wcag:{{ page.test_mode }}
| result   | <One TestResult from below>

### step1-fail

| Property    | Value
|-------------|----------
| type        | TestResult
| outcome     | Failed
| description | Existen funcionalidades que no estan disponibles por teclado

### step1-fail

| Property    | Value
|-------------|----------
| type        | TestResult
| outcome     | Pass
| description | No existen funcionalidades del ratón o las existentes esta disponibles por el teclado
