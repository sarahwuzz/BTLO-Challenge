# Phishing Email Analysis – Blue Team Labs Online Write-up

## Executive Summary
This write-up covers the analysis of a phishing email challenge provided by Blue Team Labs Online (BTLO). The investigation was conducted using **PhishTool** to analyze the email header metadata, rendering, and source structure.

---

## Investigation Details

### Question 1: Who is the primary recipient of this email?
**Answer:** `Kinnar1975@yahoo.co.uk`

### Methodology & Findings
During the initial investigation, an interesting discrepancy was identified across different sections of PhishTool:

1. **Rendered Tab:** Displays `Kinnar1975@yahoo.co.uk` in the visible `To:` header of the rendered email body.
2. **Details Pane (PhishTool Left Sidebar):** Lists the recipient as `johnsmith`.
3. **Source Tab (Raw Email Headers):** The `Delivered-To` header explicitly indicates `johnsmith123@gmail.com`.

### Analysis & Explanation

