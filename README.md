# IntelliPDF

AI-powered PDF assistant for fast understanding of long documents.

IntelliPDF helps students, researchers, and professionals upload large PDFs, get concise summaries, ask grounded questions, discover insights, and generate audio podcast-style outputs.

## Why This Project

Reading 200+ page PDFs manually is slow and error-prone. IntelliPDF is designed to reduce analysis time from hours to minutes by combining document parsing, semantic retrieval, and LLM-powered responses with source traceability.

## Core Capabilities

- Upload and process PDFs up to 500 MB and up to 1000 pages
- Preserve document structure (headings, page mapping, sections)
- Auto-generate full-document and section-wise summaries
- Ask natural-language questions with page-referenced answers
- Semantic search with relevance scoring and deep links
- Insights extraction in categories:
  - Key Insights
  - Did You Know
  - Contradictions
  - Inspirations
- Podcast-style audio generation from summaries/insights
- Image extraction + OCR + AI labeling from PDF content
- Multi-document session management and metadata tracking

## Architecture Snapshot

Based on `design.md`, the system is organized as:

- Frontend: responsive web UI with PDF viewer + chat/insights/audio interactions
- Backend: FastAPI-based API layer and processing engine
- Processing modules: parsing, retrieval, Q&A, insight generation, and media utilities
- Storage model: file-based document/session storage
- Current retrieval approach: in-memory semantic similarity (future vector DB ready)

## Target Users

- Students (research papers, textbooks)
- Researchers (literature and technical documentation)
- Professionals (reports, manuals, business docs)
- Legal/analysis workflows requiring fast clause and fact discovery

## Non-Functional Targets (from requirements)

- <= 60s processing for typical 200-page PDFs
- <= 5s Q&A response for normal queries
- <= 100ms semantic search response
- Reliable error handling for malformed/corrupted PDFs
- WCAG-aligned usability and modern-browser support

## Project Scope

### In Scope

- PDF upload and processing
- AI Q&A with citations
- Semantic search and recommendation
- Insights generation
- Audio output generation

### Out of Scope (Current Version)

- Multi-user authentication/authorization
- Real-time collaboration
- Non-PDF formats
- Enterprise SSO/audit features
- Full cloud-native HA deployment

## Tech Assumptions

- Python 3.10+
- Node.js 18+
- Stable internet for LLM/TTS APIs
- API providers available (Gemini/SarvamAI as defined in specs)

## Status

This repository currently contains product and system design documentation:

- `requirements.md` - Product requirements and constraints
- `design.md` - System architecture and design decisions

Implementation should follow these docs as the source of truth.

## Success Criteria

- Extract meaningful insights from long PDFs in under 2 minutes
- Deliver high-relevance answers with source grounding
- Keep interaction simple enough for first-time users
- Maintain stable performance across core workflows

## Roadmap Ideas

- Async background processing with job queues
- Vector database integration for scalable retrieval
- Multi-user auth and role-based access
- Advanced analytics and operational monitoring
- Cloud deployment automation

## Contributing

Before coding, align changes with `requirements.md` and `design.md`.

Recommended contribution flow:

1. Validate requirement impact
2. Propose/update API and data flow in design
3. Implement incrementally with tests
4. Document behavior and constraints

## License

Add a project license (for example MIT) before public distribution.