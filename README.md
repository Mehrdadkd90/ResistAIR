# ResistAIR _ AI-Powered Image-Based Dispute Resolution Agent

## Overview

ResistAIR is a student-developed AI agent workflow designed for academic research on image-based dispute resolution in Peer-to-Peer (P2P) accommodation platforms, such as Airbnb-style services.

The workflow compares images submitted by hosts and guests during check-in and check-out situations. Its purpose is to explore whether multimodal Large Language Models (LLMs) can support the identification of visual mismatches, damage, cleanliness issues, and possible responsibility attribution.

This project is developed strictly as a Proof of Concept (POC). It is not a complete commercial system, not a final deployable product, and not intended to replace human judgment in real disputes.

---

## Academic Purpose

This workflow was created for academic and experimental purposes only. It demonstrates how an AI artifact can be designed, implemented, and evaluated using Design Science Research Methodology (DSRM) principles.

The main objective is to test whether an AI-based workflow can:

- collect host and guest image evidence
- organize submissions by reservation, role, timing, and area
- compare paired images using multimodal LLMs
- apply predefined responsibility logic
- generate structured reasoning outputs
- log results for later analysis

The system should be understood as an early-stage research prototype rather than a production-ready dispute-resolution platform.

---

## Main Features

- Telegram-based image submission
- Reservation-based case matching
- Area-based inspection logic
- Pair-wise image comparison
- Role-aware analysis using four upload types:
  - HostCheckin
  - GuestCheckin
  - GuestCheckout
  - HostCheckout
- OpenAI multimodal LLM integration
- Structured JSON output from the AI model
- Responsibility scoring logic
- Google Sheets logging for data collection and analysis
- Human-readable notifications for involved parties

---

## Workflow Logic

The agent follows a structured dispute-analysis process:

1. A user starts the workflow through Telegram.
2. The system asks for reservation information.
3. The user selects their role and upload timing.
4. The user selects the relevant inspection area.
5. The user uploads an image.
6. The system waits for the corresponding counterpart image.
7. Once both required images are available, the workflow compares them.
8. The AI model generates a structured decision.
9. The results are logged into Google Sheets.
10. The host and guest receive the decision message.

---

## Technologies Used

- n8n
- Telegram Bot API
- OpenAI API
- Google Sheets API
- JSON workflow structure

---

## Tested Models

The workflow was experimentally tested with the following OpenAI models:

- gpt-o4-mini
- gpt-4o
- gpt-5.5

These models were compared in terms of:

- visual detection accuracy
- evidence-grounded explanation
- consistency
- uncertainty handling
- token cost

---

## Important Limitations

This project has several limitations:

- It tests only a limited number of OpenAI models.
- Other models from OpenAI, Anthropic, Google, DeepSeek, and other providers were not included.
- The workflow was tested under controlled academic scenarios.
- Real-world disputes may involve poor image quality, missing context, denial of responsibility, intentional manipulation, or biased submissions.
- The system cannot guarantee legally valid or fully reliable decisions.
- Final human supervision is necessary, especially in ambiguous, contested, or high-stakes cases.

---

## Security Notice

Before uploading or sharing this workflow publicly, remove all private credentials and secrets, including:

- OpenAI API keys
- Telegram bot tokens
- Google service account credentials
- webhook URLs
- private authentication tokens

Credentials should be configured inside n8n Credentials Manager and not hardcoded into the workflow JSON.

---

## Importing the Workflow into n8n

1. Open n8n.
2. Go to **Workflows**.
3. Click **Import from File**.
4. Upload the `.json` workflow file.
5. Configure the required credentials:
   - Telegram Bot API
   - OpenAI API
   - Google Sheets API
6. Test the workflow in a controlled environment before any further use.

---

## Suggested Repository Files

A simple repository may include:

```text
README.md
workflow.json
```

Do not include `.env` files, API keys, service account private keys, or any confidential credentials.

---

## Future Improvements

Possible future improvements include:

- testing additional LLM providers
- adding a human-in-the-loop review dashboard
- improving fraud and manipulation detection
- supporting multiple images per dispute
- adding confidence scoring
- integrating appeal and escalation mechanisms
- improving real-world robustness through larger datasets

---

## Disclaimer

This is student work developed for academic research purposes only. It is a Proof of Concept and should not be used as a final product, legal decision-making tool, or fully automated dispute-resolution system without further validation, ethical review, platform governance, and human supervision.
