# EBUTTDForge Pro (v1.0.0)

### EBU-TT-D (EBU Tech 3380), W3C IMSC1 & Broadcast Subtitling Studio

---

## Overview

**EBUTTDForge Pro** is a broadcast engineering utility and command-line tool built for European and global broadcasters, OTT streaming architects, localization post-houses, and FAST channel operators. It provides automated XML authoring, WebVTT conversion, and normative compliance checking across:

- **EBU Tech 3380**: EBU-TT-D Subtitling Distribution Format  
- **EBU Tech 3350**: EBU-TT Subtitling Format Definition  
- **W3C TTML2 / IMSC 1.1**: Internet Media Subtitles and Captions (Text Profile)  
- **Apple HLS (RFC 8216bis)**: `#EXT-X-MEDIA:TYPE=SUBTITLES` Ingest  
- **MPEG-DASH (ISO/IEC 23009-1)**: `AdaptationSet` (`application/ttml+xml`)

---

## Core Capabilities

1. **EBU-TT-D XML Authoring & Compilation**:  
   - Generates compliant EBU-TT-D XML structures with custom styling, font colors, and screen regions.  
   - Enforces the normative `urn:ebu:tt:distribution:2014-01` profile declaration.  
2. **WebVTT to EBU-TT-D Converter**:  
   - Converts standard WebVTT cue lists directly into structured EBU-TT-D paragraphs with preserved timestamps.  
3. **OTT Manifest Exporter**:  
   - Generates production-ready Apple HLS `#EXT-X-MEDIA` tags and MPEG-DASH `AdaptationSet` XML blocks.  
4. **10-Point Normative Compliance Auditor**:  
   - Automated pass/fail verification checking root elements, namespaces, language codes, layout sections, and temporal anchors.  
5. **Standalone Python CLI (`ebutt-cli.py`)**:  
   - Headless conversion, template generation, and manifest synthesis for automated CI/CD broadcast pipelines.

---

## Getting Started

### Web Studio

Open `source-code/index.html` in any web browser. Runs 100% locally with zero external network dependencies.

### Command-Line Interface

\# Convert WebVTT file to EBU-TT-D

python3 build/ebutt-cli.py convert /path/to/subtitles.vtt \--lang "es"

\# Generate sample template

python3 build/ebutt-cli.py template \--title "Live Match" \--lang "en"

\# Generate manifest tags

python3 build/ebutt-cli.py manifest \--lang "en" \--name "English" \--uri "subs/en/index.m3u8"

### Automated Testing

python3 test\_ebutt.py