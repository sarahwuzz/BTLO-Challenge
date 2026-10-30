# Phishing Email Analysis – Blue Team Labs Online Write-up

## Executive Summary
This write-up covers the analysis of a phishing email challenge provided by Blue Team Labs Online (BTLO). The investigation was conducted using **PhishTool** to analyze the email header metadata, rendering, and source structure.

## Investigation Details

### Question 1: Who is the primary recipient of this email?
**Answer:** `Kinnar1975@yahoo.co.uk`

### Methodology & Findings
During the initial investigation, an interesting discrepancy was identified across different sections of PhishTool:

1. **Rendered Tab:** Displays `Kinnar1975@yahoo.co.uk` in the visible `To:` header of the rendered email body.
2. **Details Pane (PhishTool Left Sidebar):** Lists the recipient as `johnsmith123@gmail.com`.
3. **Source Tab (Raw Email Headers):** The `Delivered-To` header explicitly indicates `johnsmith123@gmail.com`.

### Analysis & Explanation

#### Understanding the Email Structure

To understand why `johnsmith123@gmail.com` appears in the `Delivered-To` header while `Kinnar1975@yahoo.co.uk` appears in the rendered body, we must analyze the nature of the email artifact.

#### 1. The Email Type: Non-Delivery Report (Bounce Email)
The sample provided is a **Bounce Email** (also known as a *Non-Delivery Report* or *NDR*), automatically generated and sent by a **Mailer-Daemon** (Mail Transfer Agent). 

#### 2. Analyzing the Recipient Discrepancy
* **Original Intended Recipient `Kinnar1975@yahoo.co.uk`:** 
  This was the original destination address where a previous email was supposed to be delivered. The rendered email body shows this address because it includes the attached/quoted content of the failed original delivery attempt.
  
* **Actual Mailbox / Investigator Perspective `johnsmith123@gmail.com`:** 
  Because the original email failed to reach Kinnar, the mail server's `Mailer-Daemon` generated a bounce notification and sent it back to the original sender—**John Smith**. 

#### Conclusion
In this scenario, from our investigative perspective, **John Smith** is the recipient of the system notification `Delivered-To: johnsmith123@gmail.com`, while **Kinnar** was the **primary target/intended recipient** of the underlying message that failed to deliver.

### Question 2: What is the subject of this email?
**Answer:** Undeliverable: Website contact form submission

As shown at the top-right side of the Rendered tab in PhishTool, the email headers explicitly display.

### Question 3: What is the date and time the email was sent?
**Answer:** 18 March 2021 04:14

This answer was extracted from the Source tab in PhishTool, where the bottom section clearly displays `Sent: 18 March 2021 04:14`.

### Question 4: What is the Originating IP? 
**Answer:** `103.9.171.10`

This answer was extracted from the `X-Originating-IP` header, which reveals the sender's original IP address when the email was initially composed or sent via the webmail service.

### Question 5: Perform reverse DNS on this IP address, what is the resolved host?
**Answer:** `c5s2-1e-syd.hosting-services.net.au`

As previously mentioned, BTLO recommended to using `whoisdomaintools` to perform reverse DNS.

### Question 6: What is the name of the attached file?
**Answer:** Website contact form submission.eml
