VOX AI PWA 0.7 — prototipo de interfaz para iPhone

QUÉ INCLUYE ESTA VERSIÓN
- Todas las pantallas y funciones de interfaz incluidas en 0.6.
- Centro de asistentes con dos roles diferenciados:
  1) VOX AI Assistant: respuestas sobre la reunión, con evidencia temporal y enlace al audio (arquitectura objetivo; motor aún no conectado).
  2) ChatGPT Connected: consultas de conocimiento general usando contexto que el usuario decida compartir (conexión real aún no implementada).
- Preferencia de asistente: VOX, ChatGPT o ambos.
- Preferencia de respuesta: pantalla, auriculares o ambos.
- Preferencia de modo privado: no usar el altavoz del teléfono.
- Consulta rápida durante la reunión.
- Preferencias guardadas localmente en el navegador.

IMPORTANTE: QUÉ FUNCIONA Y QUÉ NO
La grabación web, pausa/reanudación, guardado local, reproducción y exportación/compartir son las funciones implementadas en esta base, sujetas a las limitaciones de Safari/iOS. Las pantallas de asistentes, consulta rápida, transcripción, traducción, diarización, preguntas IA y salida por auriculares son prototipos de interfaz/configuración. No se conectan a OpenAI ni a ChatGPT todavía. No introduzcas claves API en el navegador.

ARQUITECTURA RECOMENDADA PARA LA VERSIÓN FUNCIONAL
1. Cliente iPhone: captura de audio, controles de grabación, transcripción visible, consulta privada y reproducción.
2. Backend seguro: autenticar usuarios, emitir credenciales temporales para sesiones de audio, proteger claves API, controlar cuotas, cifrar datos y gestionar borrado.
3. Transcripción en vivo: OpenAI Realtime transcription (documentación actual recomienda gpt-live-transcribe). Esta modalidad emite texto incremental, pero no incluye etiquetas de hablante ni marcas de tiempo a nivel de palabra; se deberá añadir segmentación/diarización compatible o procesar el archivo después.
4. Traducción en vivo: flujo dedicado de Realtime translation o motor de traducción separado. Conservar siempre audio y transcripción originales; almacenar traducción como campo separado.
5. Diarización: procesar segmentos con un flujo compatible con etiquetas de hablante. No asumir que la transcripción Realtime básica identifica voces.
6. Preguntas VOX: recuperar segmentos relevantes de la transcripción de la reunión y responder con citas de segmento, hablante, tiempo y control para reproducir el audio correspondiente. Si no existe evidencia, responder que no se puede confirmar.
7. ChatGPT Connected: investigar y solicitar acceso al programa/flujo oficial Sign in with ChatGPT y permiso opcional de uso del plan. La disponibilidad depende de elegibilidad, integración y aprobación. No implica acceso al historial ni memorias de ChatGPT. Alternativa compatible: API de OpenAI pagada por VOX AI, con cobro y límites propios.
8. Voz privada: generar respuesta hablada y reproducirla en una ruta de audio seleccionada por el usuario. Probar en iPhone real con auriculares Bluetooth/cable, interrupciones, llamadas entrantes, bloqueo de pantalla y grabación simultánea. No prometer operación en segundo plano hasta superar pruebas.

DOCUMENTACIÓN OFICIAL CONSULTADA
- Realtime transcription: https://developers.openai.com/api/docs/guides/realtime-transcription
- Audio and voice: https://developers.openai.com/api/docs/guides/audio
- Realtime API: https://developers.openai.com/api/docs/guides/realtime
- Sign in with ChatGPT: https://learn.chatgpt.com/docs/sign-in-with-chatgpt
- Sign in with ChatGPT developer cookbook: https://developers.openai.com/cookbook/articles/sign-in-with-chatgpt

INSTALACIÓN DE LA PWA
1. Publica el contenido de la carpeta en alojamiento HTTPS.
2. Abre la dirección en Safari en el iPhone.
3. Permite el micrófono.
4. Compartir > Añadir a pantalla de inicio.
5. Prueba primero una grabación breve y exporta una copia.

LIMITACIONES IMPORTANTES
- No es una app nativa de App Store.
- iOS/Safari puede suspender páginas y limitar micrófono, almacenamiento y reproducción en segundo plano.
- No grabes conversaciones sin el consentimiento requerido y sin cumplir las leyes aplicables.
- No uses la aplicación para decisiones críticas sin revisar la transcripción y el audio original.
- Esta versión no ha sido probada en un iPhone real ni conecta servicios de IA.
