# CEFN Certificate Generator

Automated certificate generation for Texas A&M Center of Excellence in Forensic Nursing webinars.

## How It Works

1. Learner completes a Qualtrics evaluation after a webinar
2. Qualtrics redirects them to this page with their details in the URL
3. The certificate renders instantly in their browser
4. They click "Download Certificate (PDF)" to save it

## Certificate Types

- **Continuing Education (CE)** - College of Nursing
- **Continuing Medical Education (CME)** - Naresh K. Vashisht College of Medicine
- **Certificate of Attendance** - College of Nursing

Each type supports both Live and Enduring formats.

## Adding a New Webinar

Edit `index.html` and add an entry to the `WEBINAR_CONFIG` object at the top of the script:

```javascript
{
  id: "your-webinar-id-2026",
  title: "Full Webinar Title Here",
  presenters: "Name One, Name Two",
  liveDate: "Month Day, Year",
  ceHours: 2,
  cmeHours: 2,        // Set to null if CME is not offered
},
```

Then create two Qualtrics links with embedded data:
- **Live:** `webinar_id=your-webinar-id-2026 & format=live & presenter_1=Name+One & presenter_2=Name+Two`
- **Enduring:** `webinar_id=your-webinar-id-2026 & format=enduring & presenter_1=Name+One & presenter_2=Name+Two`

## URL Parameters

| Parameter | Description | Example |
|-----------|-------------|---------|
| `name` | Learner's full name and credentials | `Jane+Doe%2C+RN` |
| `webinar` | Webinar ID from config | `legal-edge-2026` |
| `credit` | Credit type: CE, CME, or ATTENDANCE | `CE` |
| `format` | live or enduring | `live` |

## Contact

forensicnursing@tamu.edu
