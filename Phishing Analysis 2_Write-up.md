# Phishing Analysis 2 - Blue Team Labs Online Write-up

## Executive Summary

This write-up covers the analysis of a phishing email 2 challenge provided by Blue Team Labs Online (BTLO).
The investigation was conducted using **Phishtool** to analyze email header metadata, rendering, and source structure.

## Investigation Details

### Question 1: What is the sending email address?
**Answer:** `amazon@zyevantoby.cn`

As shown at the top-left side of phishtool, clearly displays `From amazon@zyevantoby.cn`

### Question 2 : What is the recipient email address?
**Answer:** `saintington73@outlook.com`

This information is explicitly displayed in the 'To' header within the Phishtool details pane, confirming the intended recipient of the message.

### Question 3 : What is the subject line of the email?
**Answer:** `your account has been locked`

The subject line is clearly visible in the 'Subject' field within the Source tab.

### Question 4 : What the company is the attacker trying to imitate?
**Answer:** `Amazon`

The threat actor uses Amazon's branding and visual cues in the rendered tab to establish false credibility and deceive the recipient.

### Question 5 : What is the date and time the email was sent?
**Answer:** `Wed, 14 Jul 2021 01:40:32 +0900`

The exact dispatch timestamp is located in the 'Date' field within the Source tab.

### Question 6 : What is the URL of the main call-to-action button? 
**Answer:** `https://emea01.safelinks.protection.outlook.com/?url=https%3A%2F%2Famaozn.zzyuchengzhika.cn%2F%3Fmailtoken%3Dsaintington73%40outlook.com&data=04%7C01%7C%7C70072381ba6e49d1d12d08d94632811e%7C84df9e7fe9f640afb435aaaaaaaaaaaa%7C1%7C0%7C637618004988892053%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=oPvTW08ASiViZTLfMECsvwDvguT6ODYKPQZNK3203m0%3D&reserved=0`

### Analysis & Explanation

The Call To Action (CTA) button serves as the primary mechanism for user interaction within the phishing lure.
In this attack scenario, the threat actor embedded a malicious hyperlink within the "Review Account" element.

When clicked, this URL is designed to redirect the victim away from legitimate infrastructure to an attacker-controlled landing page, effectively initiating the credential harvest or malware delivery phase.

<img width="954" height="718" alt="Screenshot 2026-11-13 103502" src="https://github.com/user-attachments/assets/08bef180-fa7f-4cec-b65c-bae847b99f5f" />

### Question 7 : Look at the URL using URL2PNG. What is the first sentence (heading) displayed on this site? (regardless of whether you think the site is malicious or not)
**Answer:** `This web page could not be loaded.`

### Question 8 : When looking at the main body content in a text editor, what encoding scheme is being used?
**Answer:** `base64`
