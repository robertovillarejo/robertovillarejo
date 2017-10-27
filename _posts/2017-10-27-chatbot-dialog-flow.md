---
layout: post
title:  "Diseño del flujo de conversación de un chatbot"
date:   2017-10-27 17:22:40 +0000
categories:
---

Poner en marcha un chatbot no es una tarea trivial, es necesario entender completamente el dominio que este manejará y diseñar un flujo de conversación atractivo pero sobre todo útil para el usuario.

Durante la búsqueda de las mejores prácticas para diseñar un flujo de conversación encontré dos artículos interesantes que proporcionan ejemplos de cómo diseñarlo.

## User intents
Cuando un usuario le hace una pregunta a un chatbot lo hace con una intención específica, por ejemplo, obtener información sobre un servicio, ordenar una pizza, hacer una llamada telefónica, etc. a esto se le conoce como _user intent_.

El _intent_ nos dice cuál es el objetivo del usuario con esa pregunta, sin embargo, usualmente se necesita información adicional para procesar esa petición. Por ejemplo, es claro que el _intent_ de las preguntas "Quiero que hagas una llamada", "Llámale por favor" es **llamar** pero para la realización (_fullfillment_) de la petición necesitamos más datos: ¿a quién debo llamar?, que puede ser el nombre de una persona ó ¿a qué número debo marcar? Incluso habiendo especificado el contacto siendo la petición "Márcale a mamá" podría ser el caso que el contacto tiene asociados más de un número telefónico y entonces solicitar la información faltante.

## Key user inputs
En un intento de poner el problema en términos de _software_ podríamos decir que un _intent_ es un caso de uso del chatbot. Y que cada _intent_ tiene parámetros (_key_user_inputs_) obligatorios y opcionales. Y que dependiendo del valor de los parámetros o de la ausencia/presencia de los mismos se llevan a cabo diferentes realizaciones (o _fullfillments_).

Algunos ejemplos de _key user inputs_ para el _intent_ "Llamar":
1. A quién llamar (contacto)
2. A dónde llamar (al trabajo, a la casa, al móvil ó un número telefónico dictado)

## Design flow
El objetivo de esta fase es diseñar los diferentes flujos que podría tomar una conversación para cada _intent_, tomando en cuenta los diferentes _key user inputs_.

### The 5 W's
Para diseñar el flujo de la conversación nos podemos apoyar de las 5 W's. Éste es un _framework_ conformado por los bloques _Who, What, Where, When y Why_. Estas cinco W's nos ayudan a diseñar mejores preguntas para guiar al usuario del chatbot.

### Leading question
La pregunta principal (_leading question_) es la pregunta inicial de la conversación y se encuentra a cargo del chatbot. Debido a su importancia, debes esmerarte en la elaboración de esta pregunta a fin de que con ella logres recopilar la información esencial para continuar con la conversación. Además siempre ten en cuenta un chatbot que brinda soporte debe hacer el menor número de preguntas posibles o los clientes lo odiarán.

## The script
Para escribir un script (o guión) del chatbot toma en cuenta los siguientes escenarios:

1. Onboarding
2. Entradas ambiguas o inexistentes
3. Verificación
4. Resolución
5. Cambiando de _intents_
6. Flujo de abandono
7. Fallback

**Onboarding**
Los usuarios primerizos de tu chatbot podrían desesperarse tratando de entender cómo es que funciona. Escribe un _script_ explicando qué hace tu bot y cómo los usuarios pueden interactuar con él. Un ejemplo puede ser de mucha ayuda.

__Hola! Soy tu asistente personal. Sólo dime a quién llamar y lo haré por ti. Puedes pedirme cosas como "Llama a mamá al trabajo"__

**Entradas ambiguas o inexistentes**
Asume siempre que los usuarios van a olvidar proporcionar _key inputs_ o a obviarlas. Escribe un _script_ para cada caso en que el usuario olvida u omite información. Por ejemplo:

1. Falta a quién llamar: "¿A quién debo llamarle?" ó "Ok, a ¿quién?"
2. El contacto tiene más de un teléfono: "¿Le llamo al móvil?", "¿A dónde le llamo? (Casa, Trabajo, Móvil)"

**Verificación**
En algunos casos, es deseable que el usuario confirme lo que el chatbot ha "entendido" antes de realizar la siguiente acción. Por ejemplo, cuando se está comprando en línea quizás desees confirmar el pedido junto con el costo.

**Resolución y siguiente _intent_**
¿Qué debe decir tu bot luego de cumplir con la petición del usuario?

Por ejemplo, "Ok, llamando al móvil de mamá..."

Si planeas cambiar de _intent_ luego de la resolución, haz que el chatbot dirija la conversación hacia este.

**Cambiando entre _intents_**

**Flujo de abandono**
Quizás desees guardar el estado de una conversación sin terminar. Por ejemplo, si la petición de hace 20 minutos fue "Llámale al trabajo" y el usuario no proporcionó "a quién" probablemente quieras que el chatbot diga algo como:

- "Oye, ibas a llamarle a alguien. ¿Aún quieres hacerlo?"
  + No
  + Sí, a papá.

**Fallback**
Diseña un _script_ en el que tu chatbot no tiene ni idea de cómo responder. Esto sucederá más de lo que te imaginas.

## Referencias
[Designing chatbots](https://uxdesign.cc/how-to-design-a-robust-chatbot-interaction-8bb6dfae34fb)
[Want to design better chatbot dialog? Use the ‘Five W’s’ framework](https://blog.prototypr.io/design-better-chatbot-dialog-using-the-five-ws-framework-628bda212f39)
