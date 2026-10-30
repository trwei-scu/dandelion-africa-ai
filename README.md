# Dandelion Africa - AI for Social Impact

CSEN 166: Artificial Intelligence  
Term Team Project for Social Impact (TTP4SI)  

## Project Overview

Our team is working on the Dandelion Africa challenge, which focuses on using artificial intelligence to transform WhatsApp group communications into structured records of field activities and outcomes.

Dandelion Africa is a Kenya-based organization that supports community health, women's livelihoods, youth, and advocacy. Our proposed system aims to help organize information reported through WhatsApp and make it easier for staff to review activities and measure outcomes.

## Week 5 - Scope and Project Plan

### 1. Problem Formulation

WhatsApp messages often contain useful information about community outreach, health services, meetings, referrals, and other field activities. However, these reports can be scattered across informal messages, making them difficult to organize and verify.

Our goal is to develop an AI pipeline that can identify relevant activities within WhatsApp messages and convert them into consistent structured records while protecting personal information.

### 2. Intended Users

The primary intended users are Dandelion Africa staff, program coordinators, and field supervisors who need to review and organize community activity reports.

The system should reduce manual work while allowing human users to verify AI-generated records before they are accepted.

### 3. Definition of Success

A successful solution should:
- Identify messages containing relevant field activities.
- Exclude irrelevant conversations.
- Remove or mask sensitive personal information.
- Extract key information, including activity type, date, location, and measurable outcomes.
- Avoid creating duplicate records for the same event.
- Flag uncertain or incomplete records for human review.

The system should produce accurate, understandable, and verifiable outputs.

### 4. Proposed Technical Approach

We propose a multi-stage processing pipeline:

1. Data input: Load synthetic WhatsApp text messages and, eventually, transcripts of audio messages.
2. Message filtering: Identify which messages are related to field activities.
3. Anonymization: Detect and mask sensitive personal information.
4. Event identification: Determine which messages describe activities and group related messages when appropriate.
5. Information extraction: Extract activity type, date, location, participant counts, referrals, and other reported outcomes.
6. Deduplication: Identify repeated reports about the same event.
7. Confidence and verification: Mark uncertain results and allow human review.
8. Structured output: Save records in a standardized JSON or CSV format.

### 5. Proposed Baseline Model

Our initial baseline will use a simple rule-based Python system rather than a complex AI model.

The baseline will:
- Use keywords to identify potentially relevant messages.
- Use regular expressions to identify and mask phone numbers and similar sensitive patterns.
- Extract basic numbers and activity keywords.
- Generate structured JSON records.

This approach provides a simple, interpretable starting point for evaluating improvements.

A future version may use natural language processing or language models to improve event classification and information extraction.

### 6. Proposed Data

Because Dandelion Africa's real WhatsApp data cannot be exported to the United States under the stated data-sharing restrictions, we plan to work with synthetic data.

Our initial dataset will consist of fictional WhatsApp-style messages representing:
- Community health visits.
- Referrals to health facilities.
- Women's livelihood activities.
- Community outreach events.
- Irrelevant everyday conversation.
- Repeated reports about the same event.
- Messages containing fictional personal details for anonymization testing.

We will begin with text messages and consider audio transcription as an extension if time permits.

We will avoid uploading identifiable real conversations or sensitive personal information to GitHub.

### 7. Proposed Evaluation Metrics

We plan to evaluate the system using the following metrics:

- Classification precision: Of the messages identified as relevant, how many are actually relevant?
- Classification recall: Of all relevant messages, how many were identified?
- Extraction accuracy: How often are activity fields extracted correctly?
- Anonymization recall: How many sensitive personal details are correctly detected and masked?
- Duplicate detection accuracy: How well does the system identify repeated event reports?

We will compare system outputs against manually labeled expected outputs in a synthetic development dataset.

### 8. Technical Challenges

Potential challenges include:
- Informal language, spelling variations, and incomplete messages.
- Audio messages and different English accents.
- Messages describing multiple events.
- Multiple messages describing the same activity.
- Missing or ambiguous dates and locations.
- Preventing hallucinated or unsupported information.
- Balancing privacy protection with preserving useful activity data.

### 9. Team Responsibilities

**Responsibilities**
- Tess: Data creation and data preparation
- Terrence: Message filtering and classification
- Eric: Anonymization and information extraction
- Everyone: Evaluation, testing, and integration 

### 10. Cross-Team Discussion

- Might be difficult to distinguish relativity
- WhatsApp messages are often informal and may include spelling errors or abbreviations
- For initial baseline we want to see if we can use key words to filter since it is simple to implement
- Since we don't have access to Dandelion Africa's original WhatsApp data, we will discuss how to out source or create our own

Questions for other teams:
- What information should a structured activity record contain?
- How will you handle messages that describe the same activity?
- How will you evaluate anonymization without real private data?
- What is the simplest useful baseline?

### 11. Next Steps - Week 6

Our next goal is to implement a working baseline.

Planned tasks:
1. Create an initial synthetic dataset.
2. Implement basic message filtering.
3. Implement simple anonymization.
4. Extract selected activity attributes.
5. Produce JSON output.
6. Test the pipeline on sample messages.

## References

- Dandelion Africa: https://dandelionafrica.org/
- CSEN 166 Term Team Project for Social Impact assignment

## Weekly Progress

- Week 5: Initial project scope and proposed approach.
- Week 6: To be completed.
- Week 7: To be completed.
- Week 8: To be completed.
- Week 9: To be completed.
- Week 10: To be completed.
