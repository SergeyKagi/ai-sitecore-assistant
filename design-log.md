# Design Log

## Decision #001 — Use JSON as the intermediate format

### Problem

The AI output needs to be passed to other parts of the system, such as validators, mappers, browser automation, or Sitecore API integration.

### Decision

Use structured JSON as the intermediate format between the LLM and the execution layer.

### Reason

- Easy to validate
- Easy to debug
- CMS-independent
- Can be mapped to Sitecore components later
- Can be reused for other CMS platforms

### Consequences

The project needs a JSON schema and validation rules.