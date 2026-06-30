# Architecture

## Current concept

The system should not send marketing content directly from an LLM into Sitecore.

Instead, the LLM should first produce structured data.

Marketing document
→ Content Parser
→ LLM Parser
→ Structured JSON
→ JSON Validator
→ Component Mapper
→ Sitecore Draft Page
→ QA Checks

## Main modules

### Content Parser

Extracts text and assets from source files such as Word documents.

### LLM Parser

Analyzes the content and converts it into structured page data.

### JSON Validator

Checks that the AI output follows the required schema.

### Component Mapper

Maps abstract page components to real Sitecore components.

### Sitecore Execution Layer

Creates or updates draft pages in Sitecore.

### QA Layer

Checks SEO, required fields, links, alt text, CTA, and page structure.