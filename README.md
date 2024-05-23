# Email Verifier

Email Verifier is a simple Go application that checks the presence of DNS records for a given domain. It verifies the existence of MX, SPF, and DMARC records and prints the results in CSV format.

## Features

- Verifies the existence of MX records.
- Checks for SPF records and retrieves the SPF record if it exists.
- Checks for DMARC records and retrieves the DMARC record if it exists.

## Prerequisites

- Go (version 1.13 or later)

## Installation

1. Clone the repository:

```bash
git clone https://github.com/likhithkp/go-email-verification-tool.git
cd go-email-verification-tool
```

## Run

```go run main.go```

## Example input:
  example.com
  google.com
  yahoo.com

## Example output:
  domain, hasMX, hasSPF, spfRecord, hasDMARC, dmarcRecord
  example.com, true, true, v=spf1 include:_spf.example.com ~all, true, v=DMARC1; p=none; rua=mailto:dmarc@example.com
  google.com, true, true, v=spf1 include:_spf.google.com ~all, true, v=DMARC1; p=none; rua=mailto:dmarc-reports@google.com
  yahoo.com, true, true, v=spf1 include:spf.protection.outlook.com -all, true, v=DMARC1; p=reject; rua=mailto:dmarc@reporting.yahoo.com

