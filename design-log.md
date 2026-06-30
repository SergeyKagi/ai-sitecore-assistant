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

## Decision #002 — Use structured JSON instead of HTML as the primary AI output

### Problem

The AI needs to convert marketing content into a format that can later be used by Sitecore, Umbraco, Contentful, AEM, or another CMS.

### Considered options

#### HTML

Pros:
- Easy to preview
- Close to the final page output
- Useful for simple rich text blocks

Cons:
- Harder to map to CMS components
- Repeated tags can create ambiguity
- Does not clearly separate content meaning from presentation
- Less suitable for complex page structures

#### JSON

Pros:
- CMS-independent
- Clearly separates content into fields and components
- Easier to validate
- Easier to map to different CMS platforms
- Better for automation and QA checks

Cons:
- Not directly previewable without an additional renderer
- Requires a schema and validation layer

### Decision

Use JSON as the primary AI output format.

HTML can still be used inside specific fields when the CMS field expects rich text content.

### Consequences

The system needs:
- JSON Schema
- validation rules
- component mapping logic
- optional preview renderer