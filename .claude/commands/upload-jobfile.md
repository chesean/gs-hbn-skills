# Upload Jobfile to CXTM

Upload a local `jobfile.robot` to CXTM project 21534 by jobfile ID.

## Usage
```
/upload-jobfile <jobfile_id>
```

---

## Critical Facts

| Item | Value |
|------|-------|
| Tool | CXTM MCP `update_jobfile_content` (NOT Playwright, NOT HTTP PATCH) |
| Auth | `cxtm_api_token="YOUR_API_KEY_HERE"` |
| Source file | `jobfile.robot` (NOT `jobfile-old.txt`) |
| Jobfile ID | From folder name OR Known ID Mappings table below |

---

## Steps

**1. Find local folder**
```
Glob pattern: 21534-*-<testcase_id>
```
Or use Known ID Mappings if jobfile ID is already known.

**2. Read content**
```
Read: <local_folder>/jobfile.robot
```

**3. Upload via CXTM MCP**
```
mcp__hub__cxtm__update_jobfile_content(
  input_data={"jobfile_id": <JOBFILE_ID>, "content": "<file_content>"},
  cxtm_api_token="YOUR_API_KEY_HERE"
)
```

Success response: `{"id": <JOBFILE_ID>, "name": "...", "project_id": 21534, ...}`

---

## Known ID Mappings (P1.55-P1.70)

| Folder | Jobfile ID | Type |
|--------|-----------|------|
| 21534-P1.55-1829255 | 800648 | DOWN AGG1 - CORE1-C9508 |
| 21534-P1.56-1829256 | 800649 | UP AGG1 - CORE1-C9508 |
| 21534-P1.57-1829257 | 800650 | DOWN AGG1 - CORE2-C9504 |
| 21534-P1.58-1829258 | 800651 | UP AGG1 - CORE2-C9504 |
| 21534-P1.59-1829259 | 800652 | DOWN AGG1 - CORE3-C9364C-GX |
| 21534-P1.60-1829260 | 800653 | UP AGG1 - CORE3-C9364C-GX |
| 21534-P1.61-1829261 | 800654 | DOWN AGG1 - CORE4-C9364C-GX |
| 21534-P1.62-1829262 | 800655 | UP AGG1 - CORE4-C9364C-GX |
| 21534-P1.63-1829263 | 800656 | DOWN AGG2 - CORE1-C9508 |
| 21534-P1.64-1829264 | 800657 | UP AGG2 - CORE1-C9508 |
| 21534-P1.65-1829265 | 800658 | DOWN AGG2 - CORE2-C9504 |
| 21534-P1.66-1829266 | 800659 | UP AGG2 - CORE2-C9504 |
| 21534-P1.67-1829267 | 800660 | DOWN AGG2 - CORE3-C9364C-GX |
| 21534-P1.68-1829268 | 800661 | UP AGG2 - CORE3-C9364C-GX |
| 21534-P1.69-1829269 | 800662 | DOWN AGG2 - CORE4-C9364C-GX |
| 21534-P1.70-1829270 | 800663 | UP AGG2 - CORE4-C9364C-GX |
