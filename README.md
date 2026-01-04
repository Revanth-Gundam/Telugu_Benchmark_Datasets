# Telugu Language Benchmarking Datasets

This repository contains a collection of five high-quality Telugu datasets translated and romanized from standard English benchmarks. These datasets are designed to evaluate the reasoning, ethical judgment, and linguistic competence of large language models (LLMs) in the Telugu language.

## Table of Contents
1. [Telugu GSM8K (Mathematics)](#1-telugu-gsm8k-mathematics)
2. [Telugu Winogrande (Linguistic Ambiguity)](#2-telugu-winogrande-linguistic-ambiguity)
3. [Telugu ARC Science (Reasoning)](#3-telugu-arc-science-reasoning)
4. [Telugu CaseHold (Legal Reasoning)](#4-telugu-casehold-legal-reasoning)
5. [Telugu Hendrycks Ethics (Ethical Judgment)](#5-telugu-hendrycks-ethics-ethical-judgment)

---

## 1. Telugu GSM8K (Mathematics)
**File:** `telugu_gsm_math.json`

A collection of grade-school math word problems requiring multi-step reasoning.

- **Fields:**
  - `sample_id`: Unique identifier (e.g., "GSM_TE_001").
  - `original_question`: The original problem in English.
  - `telugu_question`: The translated problem in Telugu script.
  - `romanized_telugu_question`: Phonetic transliteration using standard English alphabets.
  - `final_answer`: The final numerical result.
  - `difficulty`: Complexity level ("easy", "medium" or "hard).

---

## 2. Telugu Winogrande (Linguistic Ambiguity)
**File:** `telugu_winogrande_english.json`

A benchmark for common-sense reasoning focusing on pronoun resolution and linguistic ambiguity.

- **Fields:**
  - `sample_id`: Unique identifier.
  - `eng_sent` / `eng_op1` / `eng_op2`: Original English sentence and choices.
  - `tel_sent` / `tel_op1` / `tel_op2`: Telugu translation of the sentence and options.
  - `romanized_tel_sent` / `romanized_tel_op1` / `romanized_tel_op2`: Phonetic transliteration.
  - `answer`: The correct option index ("1" or "2").

---

## 3. Telugu ARC Science (Reasoning)
**File:** `telugu_arc_science.json`

Science-based multiple-choice questions designed to test knowledge-based reasoning.

- **Fields:**
  - `sample_id`: Unique identifier.
  - `difficulty`: Difficulty level ("easy" or "hard).
  - `original_question` / `original_choices`: Original English science question and options.
  - `telugu_question` / `telugu_choices`: Telugu translation of the question and options.
  - `romanized_telugu_question` / `romanized_telugu_choices`: Phonetic transliteration.
  - `answer_key`: The correct alphabetical choice (e.g., "A", "B", "C", "D" or "1", "2", "3", "4").

---

## 4. Telugu CaseHold (Legal Reasoning)
**File:** `telugu_casehold_law.json`

Legal reasoning tasks requiring identification of the correct legal holding based on a judicial citation prompt.

- **Fields:**
  - `sample_id`: Unique identifier.
  - `original_citation_prompt` / `original_holdings`: Original English legal context and holdings.
  - `telugu_prompt` / `telugu_holdings`: Telugu translation of the legal prompt and options.
  - `romanized_telugu_prompt` / `romanized_telugu_holdings`: Phonetic transliteration.
  - `correct_label`: Index of the correct holding (0 through 4).

---

## 5. Telugu Hendrycks Ethics (Ethical Judgment)
**File:** `telugu_hendrycks_ethics.json`

Evaluates model alignment with human ethical perspectives across four sub-domains.

### Sub-Category Label Details:

#### **A. Commonsense**
- **Fields:** `original_input`, `tel_input`, `romanized_tel_input`, `label`.
- **Label 1**: Action is **unacceptable** or morally questionable.
- **Label 0**: Action is **acceptable** or neutral.

#### **B. Deontology**
- **Fields:** `original_input` (scenario, excuse), `tel_input` (tel_scenario, tel_excuse), `romanized_tel_input` (romanized_tel_scenario, romanized_tel_excuse), `label`.
- **Label 1**: The **excuse is reasonable**/justified for the given scenario.
- **Label 0**: The **excuse is unreasonable**/unjustified.

#### **C. Justice**
- **Fields:** `original_scenario`, `tel_scenario`, `romanized_tel_scenario`, `label`.
- **Label 1**: Scenario describes a **just** or fair situation.
- **Label 0**: Scenario describes an **unjust** situation or violation of fairness.

#### **D. Utilitarianism**
- **Fields:** `original_input` (baseline, less_pleasant), `tel_input` (tel_baseline, tel_less_pleasant), `romanized_tel_input` (romanized_tel_baseline, romanized_tel_less_pleasant).
- The `less_pleasant` scenario is indeed **worse/less desirable** than the `baseline`.


---

## Usage for Inference
These datasets support evaluation in both native Telugu script and phonetic Romanized forms. Romanized fields use only standard English alphabets (a-z, A-Z) with no accents or diacritics to ensure maximum compatibility across different tokenizers.
