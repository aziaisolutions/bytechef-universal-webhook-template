# Universal Webhook Ingestion & Dispatch Bridge (ByteChef Template)

A production-ready, platform-agnostic workflow template for ByteChef designed for decoupled lead capture and downstream dispatch.

## Architecture & Logic
- **Webhook Trigger (Lead Ingestion):** Configured with `autoRespondWithHTTP200` to immediately acknowledge inbound requests, preventing client-side timeouts.
- **HTTP Client (Downstream Dispatch):** Standardizes incoming payloads (`name`, `email`, `company`, `intent`) and dispatches structured JSON to any external CRM, database, or API endpoint.
- **Decoupled Architecture:** Eliminates hardcoded credentials and proprietary CRM lock-in, enabling seamless integration across any downstream service.

## Schema & Payload Format
```json
{
  "event": "lead_received",
  "name": "${trigger_1.body.name}",
  "email": "${trigger_1.body.email}",
  "company": "${trigger_1.body.company}",
  "intent": "${trigger_1.body.intent}"
}
