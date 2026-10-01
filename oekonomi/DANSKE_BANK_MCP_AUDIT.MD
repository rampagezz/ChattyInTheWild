# Danske Bank MCP (Model Context Protocol) & Revisionslog

> **Status:** Pilot Integration Forberedt  
> **Protokol:** Model Context Protocol (MCP) via OAuth 2.0 & mTLS (QWAC / EV Certifikat)  
> **Ansvarlig agent:** Heimdal (Bank-Gatekeeper)  
> **Sikkerhedsniveau:** HØJESTE (Read-Only Transaktionsadgang)

---------------------------

## 🛡️ Sikkerhedsdeklaration & Begrænsninger
1. **Læseadgang:** Agenterne har udelukkende adgang til værktøjerne `get_account_balance` og `list_transactions`.
2. **Ingen direkte hævninger:** Agenten kan IKKE overføre penge selvstændigt.
3. **Revisionsspor (Audit Log):** Alle kald registreres med nøjagtigt tidsstempel, formål og modtagende agent.

---------------------------

## 📋 Værktøjer eksponeret via Danske Bank MCP Server:
- `get_account_balance`: Returnerer realtidssaldo for erhvervskontoen (DKK).
- `list_transactions`: Trækker seneste posteringer ud til brug for Veras automatiske bankafstemning i Dinero.
- `initiate_payment`: Klargør betalingsforslag (kræver altid manuel godkendelse af Kenneth i Danske Bank District).

---------------------------

## 📝 Seneste Revisionslog (Audit Trail)
- **[2026-09-29 08:30:00]** Heimdal etablerede sikker mTLS handshake til Danske Bank MCP Gateway.
- **[2026-09-29 08:30:15]** `get_account_balance` kaldt. Status: OK. Saldo synkroniseret til Pennys likviditetsoverblik.
- **[2026-09-29 08:31:00]** `list_transactions` hentede 5 seneste poster. Overdraget til Vera for Dinero-afstemning.
