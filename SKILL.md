---
name: iptc-metadata-skill
description: Expert guidance on the IPTC Photo Metadata Standard (Core 1.5 and Extension 1.9), including property definitions, XMP/IIM/JSON mappings, TechReference usage, controlled vocabularies, rights and licensing metadata, accessibility guidance, and AI-generated image metadata (Digital Source Type and AI fields). Use when tasks mention IPTC Photo Metadata, IPTC Core/Extension, XMP/IPTC metadata, embedding photo metadata, IPTC fields, TechReference, or when mapping or validating photo metadata properties.
---

# IPTC Photo Metadata Skill

## Workflow

1. Clarify the goal: authoring metadata, mapping fields to XMP/IIM/JSON, validating existing metadata, or answering field definitions.
2. Identify the schema: Core (IIM heritage, backward compatible) or Extension (newer, more granular, includes PLUS rights).
3. For property definitions, data types, cardinality, and mappings, consult the TechReference JSON or YAML listed in `references/standard-overview.md` (use the cached copies in `references/` when offline).
4. For best-practice guidance (minimal fields, AI guidance, accessibility fields, preservation), consult `references/user-guide.md`.
5. When a property is controlled by a vocabulary, return the identifier URI, not just the label.

## Tools

- Use `scripts/iptc_metadata.py` to read, write, or validate IPTC/XMP metadata via the ExifTool CLI.
- If you plan to run `scripts/iptc_metadata.py`, first read `references/tooling.md` for full usage, tag naming, and validation guidance.

## Response guidance

- Use the exact property names and schema names from the IPTC standard.
- Provide the XMP prefix and property name when mapping to XMP (for example, `Iptc4xmpExt:DigitalSourceType`).
- When using ExifTool tags, use group prefixes like `XMP-iptcExt:` (see `references/tooling.md` for the namespace mapping).
- If a field exists in both IIM and XMP, mention both mappings; if it is Extension-only, state that it is XMP-only.
- For ambiguous or legacy fields, call out the preferred modern field and explain the mapping.
- Remind that metadata should be embedded in the image file and preserved through workflows.

## References

- `references/standard-overview.md` for schema overview, spec table structure, data types, TechReference links, and XMP namespaces.
- `references/standard-overview.md` also explains Core vs Extension differences and how XMP is used (embedded vs sidecar, Core mappings vs Extension-only).
- `references/user-guide.md` for practical usage guidance, minimal set, AI metadata, Digital Source Type, controlled vocabularies, and accessibility fields.
