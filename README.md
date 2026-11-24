# Universal Webhook Ingestion & Dispatch Bridge (ByteChef Template)

A production-ready, platform-agnostic ByteChef project template for decoupled lead capture and downstream HTTP dispatch.

## How to Import in ByteChef
1. Download the `.zip` project archive from this repository.
2. Open your ByteChef dashboard and go to **Projects**.
3. Click the dropdown arrow next to **New Project** and select **Import Project**.
4. Upload the `.zip` archive — the project and workflow will load directly onto the canvas.

## Architecture & Logic
- **Webhook Trigger (`autoRespondWithHTTP200`):** Immediately acknowledges inbound POST payloads to prevent upstream client timeouts.
- **HTTP Client (Downstream Dispatch):** Maps incoming fields (`name`, `email`, `company`, `intent`) into a standardized JSON event (`lead_received`) and dispatches it to any external CRM, database, or webhook endpoint.
- **Decoupled Design:** Eliminates hardcoded credentials and proprietary CRM lock-in.

## Expected Webhook Payload
```json
{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "company": "Acme Corp",
  "intent": "demo"
}
