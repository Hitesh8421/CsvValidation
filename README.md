# CSV Upload & Date Validation — Spring Boot

**Beginner-friendly** app: upload a CSV from the browser, validate each row, return row-wise errors.

## What it checks
- Name must not be empty
- DateOfBirth must not be empty
- DateOfBirth must match yyyy-MM-dd and be a real date

## Run it
```bash
cd backend
mvn spring-boot:run
```
Open: http://localhost:8080/ (serves the UI)

## API
POST `/api/csv/upload` with multipart field `file`.

### Response
- Success: `{ "status": "success" }`
- Error:
```json
{
  "status": "error",
  "errors": [ { "row": 3, "message": "Invalid date format/value: '1994/03/30'. Expected yyyy-MM-dd" } ]
}
```

## Sample CSV
Download from the UI or use `src/main/resources/static/sample_users.csv`.
