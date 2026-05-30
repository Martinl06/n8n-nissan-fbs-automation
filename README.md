

# 🚀 Sistema Automatizado de Carga de Facturas (Simulación FBS Nissan)

Este proyecto consiste en un ecosistema backend automatizado desarrollado en **n8n** que optimiza la recepción, extracción y procesamiento cognitivo de facturas comerciales no estructuradas mediante Inteligencia Artificial, validando los datos con código para su posterior inyección en sistemas core.

## 📊 Arquitectura del Flujo

El flujo de trabajo sigue la siguiente infraestructura lógica:
1. **Webhook (Ingesta):** Recibe peticiones `POST` con la información cruda de los documentos fiscales.
2. **AI Agent (Procesamiento Cognitivo):** Integrado con `gpt-5o-mini` para la extracción selectiva de entidades clave (Proveedor, CUIT, Factura, Montos).
3. **Code Node (Sanitización):** Una función nativa en **JavaScript** con manejo de excepciones (`try/catch`) que transforma la respuesta de la IA en un formato JSON ordenado.
4. **HTTP Request (Integración API):** Carga los datos estructurados simulando la integración con el sistema core FBS.
5. **Discord Webhook (Capa de Alerta):** Notifica de forma dinámica al equipo de operaciones el éxito de la transacción.

## 🛠️ Tecnologías Utilizadas
* **n8n** (Orquestación del Workflow)
* **OpenAI API** (gpt-4o-mini)
* **JavaScript** (Sanitización y tipado de datos)
* **Postman** (Client de testing para peticiones HTTP)

## 🚀 Cómo Replicar este Proyecto
1. Descarga el archivo `n8n_nissan_fbs_automation.json` de este repositorio.
2. Abre tu instancia de n8n.
3. Crea un flujo nuevo, ve a las opciones (`...`) arriba a la derecha y selecciona **Import from file**.
4. Carga tus propias credenciales para el nodo de OpenAI y el Webhook de Discord. ¡Y listo!
