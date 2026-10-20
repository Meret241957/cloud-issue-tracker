API Test Plan

These tests define the expected behavior of the Issues API before implementation in Lab 4.

Test ID Request Expected Result
T01 GET /api/issues 200 OK; JSON array returned.
T02 POST valid title, description, and priority 201 Created; complete created issue returned.
T03 POST missing title 400 Bad Request; VALIDATION_ERROR.
T04 POST invalid priority = Critical 400 Bad Request; VALIDATION_ERROR.
T05 PATCH existing issue status = Resolved 200 OK; returned status is Resolved.
T06 PATCH status = Deleted 400 Bad Request; VALIDATION_ERROR.
T07 PATCH unknown issue ID 404 Not Found; ISSUE_NOT_FOUND.
T08 GET when no issues exist 200 OK; empty JSON array ([]).
T09 Send unexpected extra server-owned fields Server ignores or rejects them according to the API contract. The client cannot choose authoritative fields such as id, status, or createdAt.
