# Use Case Specification: UC-04 AI Agricultural Agent Advisory Consultation

> **Status**: Draft – Derived from Source File  
> **Module**: PRD / Use Case Specifications  
> **Source Reference**: `Source File.docx` (§3 F12, §4 F13-F16)

---

## 1. Actors
- **Primary Actor**: Farmer / Agronomist / Field Scout
- **Supporting Systems**: AI Agricultural Agent Conversational Service, Central Backend Database

---

## 2. Preconditions
- User is logged into the AgroScout mobile application.
- Active farm context is selected.
- Network connectivity to backend services is available.

---

## 3. Main Success Scenario (Nominal Flow)
1. User opens the AI Agricultural Agent interface from the Dashboard shortcut or menu `(Source: §3 F1, §3 F12)`.
2. User submits an inquiry in natural language regarding suspected disease symptoms (e.g., "Why are my potato leaves curling and showing dark concentric rings?") `(Source: §3 F12)`.
3. Optionally, user attaches a photo of the affected plant or links a recent inspection record `(Source: §3 F12, §4 F14)`.
4. The AI Agent ingests the inquiry, references available vision detection results, and incorporates the active farm's recent sensor context (e.g., elevated humidity readings) `(Source: §2, §3 F12)`.
5. The Agent synthesizes an agronomic guidance response structured into:
   - *Symptoms Identified*: Description of concentric foliar lesions characteristic of early blight `(Source: §3 F12)`.
   - *Etiology / Causes*: Explanation of fungal pathogen dynamics favored by warm days and high relative humidity `(Source: §3 F12)`.
   - *Potential Effects*: Anticipated yield reduction and defoliation if left untreated `(Source: §3 F12)`.
   - *Prevention & Remediation*: Targeted cultural practices (spacing, drip irrigation) and recommended chemical treatment options `(Source: §3 F12)`.
6. The Agent appends the mandatory advisory disclaimer and uncertainty notice: *"AI output is strictly advisory guidance, not a guaranteed diagnosis. Verify with a local agronomic expert before widespread application."* `(Source: §3 F12, §4 F16)`.
7. User submits follow-up questions in the multi-turn session and receives consistent contextual advice `(Source: §3 F12)`.

---

## 4. Alternative & Exception Flows
- **4a. Image Interpretation Unsupported or Inconclusive**:
  1. The attached image resolution is too degraded or out of focus for vision analysis.
  2. The Agent explicitly communicates uncertainty regarding the photo, provides general symptom possibilities based on user text, and advises capturing a clear close-up in daylight `(Source: §3 F12)`.
- **4b. User Demands Definite Certification**:
  1. User prompts the agent for absolute confirmation of a diagnosis.
  2. The Agent reasserts its role as an agricultural decision-support tool, highlights that non-specialist visual symptoms can overlap, and suggests requesting an expert review `(Source: §3 F12, §4 F4)`.
