API validation → Data layer
← Render created issue ← 201 + JSON ←───────────────┘
s → API → Data layer
← Render list ← 200 + JSON array ←───┘
Button → PATCH /api/issues/{id}/status → API validation → Data layer
← Re-render issue ← 200 + updated JSON ←──────────┘
Browser input ───── HTTP request ─────▶ REST API ─────▶ Data
▲ │
└────────── JSON response ◀────────────┘
POST /api/issues HTTP/1.1
Content-Type: application/json
Accept: application/json
{
"title": "Projector not working in Lab 3",
"description": "Laptop cannot detect the classroom projector.",
"priority": "High"
}
HTTP/1.1 201 Created
Content-Type: application/json
Location: /api/issues/ISS-102
{
"id": "ISS-102",
"title": "Projector not working in Lab 3",
"description": "Laptop cannot detect the classroom projector.",
"priority": "High",
"status": "Open",
"createdAt": "2026-10-05T08:15:00Z"
}
