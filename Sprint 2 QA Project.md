# Project 2 EC, BV, TC — v3.0

---

## Requirements Analysis

> **Task:** Decompose each requirement into atomic blocks and write them down below.

---

### Requirement ID: FR-1

| # | Atomic Block |
|---|---|
| 1 | The interface must have an input field labeled "From". |
| 2 | The interface must have an input field labeled "To". |
| 3 | The interface must have a mode option labeled "Optimal". |
| 4 | The interface must have a mode option labeled "Fastest". |
| 5 | The interface must have a mode option labeled "Custom". |
| 6 | The interface must have an icon for going on foot. |
| 7 | The interface must have an icon for the user's car. |
| 8 | The interface must have an icon for car-sharing. |
| 9 | The interface must have an icon for a taxi. |
| 10 | The interface must have an icon for a scooter. |
| 11 | The interface must have an icon for a bicycle. |

---

### Requirement ID: FR-2

| # | Atomic Block |
|---|---|
| 1 | The interface must have an input field for the departure point. |
| 2 | The interface must have an input field for the destination. |
| 3 | The interface must allow spaces at the beginning of the departure point address. |
| 4 | The interface must allow spaces at the end of the departure point address. |
| 5 | The interface must allow spaces at the beginning of the destination address. |
| 6 | The interface must allow spaces at the end of the destination address. |
| 7 | The interface must delete spaces from the departure field when it is not in focus. |
| 8 | The interface must delete spaces from the destination field when it is not in focus. |

---

### Requirement ID: FR-3

| # | Atomic Block |
|---|---|
| 1 | The interface must have an empty initial state for the "From" input field. |
| 2 | The interface must have an empty initial state for the "To" input field. |
| 3 | The interface must have an unselected initial state for the "Optimal" mode option. |
| 4 | The interface must have an unselected initial state for the "Fastest" mode option. |
| 5 | The interface must have an unselected initial state for the "Custom" mode option. |
| 6 | The interface must have an inactive initial state for the transport panel. |

---

### Requirement ID: FR-4

| # | Atomic Block |
|---|---|
| 1 | The interface must allow numbers to be entered in the "From" field. |
| 2 | The interface must allow numbers to be entered in the "To" field. |
| 3 | The interface must allow spaces to be entered in the "From" field. |
| 4 | The interface must allow spaces to be entered in the "To" field. |
| 5 | The interface must allow dashes to be entered in the "From" field. |
| 6 | The interface must allow dashes to be entered in the "To" field. |
| 7 | The interface must allow periods to be entered in the "From" field. |
| 8 | The interface must allow periods to be entered in the "To" field. |
| 9 | The interface must allow commas to be entered in the "From" field. |
| 10 | The interface must allow commas to be entered in the "To" field. |
| 11 | The interface must allow Latin characters to be entered in the "From" field. |
| 12 | The interface must allow Latin characters to be entered in the "To" field. |
| 13 | The interface must enforce a maximum length of 50 characters for the "From" field. |
| 14 | The interface must enforce a maximum length of 50 characters for the "To" field. |
| 15 | The interface must delete spaces from the "From" field when it is not in focus. |
| 16 | The interface must delete spaces from the "To" field when it is not in focus. |
| 17 | The interface must display the error message "Incorrect address." if the data in the "From" field is invalid. |
| 18 | The interface must display the error message "Incorrect address." if the data in the "To" field is invalid. |
| 19 | The interface must prevent form submission if the "From" field data is invalid. |
| 20 | The interface must prevent form submission if the "To" field data is invalid. |

---

## Test Planning

> **Task:** Scan the test plan and fill out the table by writing down the number and the name of the section where you found the relevant information.

| Information | The Section It Can Be Found In |
|---|---|
| Description of software being tested | 1.2 Application Summary |
| Person/people responsible for communicating strategic changes to the team | 4.2 Test Lead |
| Digital infrastructure used in testing | 5. Software and Hardware Resources |
| Application's features and functionalities | 1.2 Application Summary |
| Measures that should be taken to avoid delays | 6. Risk & Mitigation |

---

## Equivalence Partitions/Classes and Boundary Values

### Stage 1: Define Equivalence Partitions/Classes and Boundary Values

#### From Field

| Equivalence Class | Boundary Values |
|---|---|
| Numbers | |
| Spaces | |
| Dashes | |
| Periods | |
| Commas | |
| Latin Characters | |
| Non-Latin Characters | |
| Special Characters | |
| 0–50 Characters | 0, 1, 49, 50, 51 |
| 51+ Characters | 50, 51, 52 |
| Leading Spaces | |
| Trailing Spaces | |

#### To Field

| Equivalence Class | Boundary Values |
|---|---|
| Numbers | |
| Spaces | |
| Dashes | |
| Periods | |
| Commas | |
| Latin Characters | |
| Non-Latin Characters | |
| Special Characters | |
| 0–50 Characters | 0, 1, 49, 50, 51 |
| 51+ Characters | 50, 51, 52 |
| Leading Spaces | |
| Trailing Spaces | |

---

### Test Data

| Test Data for Equivalence Class | Test Data for Boundary Values | Comments |
|---|---|---|
| `123 Creston Street` | `123 Creston Street` | Numbers |
| `123 Creston Street` | `123 Creston Street` | Spaces |
| `123-B Creston Street` | `123-B Creston Street` | Dashes |
| `123 Creston Street.` | `123 Creston Street.` | Periods |
| `123 Creston Street, Kalamazoo` | `123 Creston Street, Kalamazoo` | Commas |
| `123 Creston Street` | `123 Creston Street` | Latin Characters |
| `123 Крестон Стрит` | `123 Крестон Стрит` | Non-Latin Characters |
| `#123 Creston Street` | `#123 Creston Street` | Special Characters |
| `123 Creston Street` (13) | `""` (0) | 0–50 chars |
| | `A` (1) | |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 4900` (49) | |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 49002` (50) | |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 49002-` (51) | |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 49002--` (52) | |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 49002----` (53) | 51+ chars |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 4900` (49) | Boundary |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 49002` (50) | Boundary |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 49002-` (51) | Boundary |
| | `123 Creston Street, Kalamazoo, Michigan, MI, 49002--` (52) | |
| `" 123 Creston Street"` | `" 123 Creston Street"` | Leading Spaces |
| `"123 Creston Street "` | `"123 Creston Street "` | Trailing Spaces |

---

## Test Cases

### Stage 2: Write Test Cases

| ID | Test Case | Precondition | Steps |
|---|---|---|---|
| example | Verify the user can enter numbers in To address field | Server started; To field is empty | Enter numbers in the To field |
| example | Verify the user can enter numbers in From address field | Server started; From field is empty | Enter numbers in the From field |
| t-1 | Verify the user can enter spaces in From address field | Server started; From field is empty | Enter an address with spaces in the From field |
| t-2 | Verify the user can enter dashes in From address field | Server started; From field is empty | Enter an address with a dash in the From field |
| t-3 | Verify the user can enter periods in From address field | Server started; From field is empty | Enter an address with a period in the From field |
| t-4 | Verify the user can enter commas in From address field | Server started; From field is empty | Enter an address with a comma in the From field |
| t-5 | Verify the user can enter Latin characters in From address field | Server started; From field is empty | Enter Latin characters in the From field |
| t-6 | Verify error when entering non-Latin characters in From field | Server started; From field is empty | Enter non-Latin characters in the From field |
| t-7 | Verify error when entering special characters in From field | Server started; From field is empty | Enter special characters in the From field |
| t-8 | Verify behavior when From field is empty (0 characters) | Server started; From field is empty | Attempt to submit or validate an empty From field |
| t-9 | Verify valid minimum boundary of 1 character in From field | Server started; From field is empty | Enter exactly 1 allowed character in the From field |
| t-10 | Verify validation at 49 characters in From field | Server started; From field is empty | Enter a 49-character valid string in the From field |
| t-11 | Verify validation at maximum boundary of 50 characters in From field | Server started; From field is empty | Enter a 50-character valid string in the From field |
| t-12 | Verify error at first invalid boundary of 51 characters in From field | Server started; From field is empty | Enter a 51-character string in the From field |
| t-13 | Verify error when input exceeds length drastically in From field | Server started; From field is empty | Enter a 53-character string in the From field |
| t-14 | Verify leading spaces remain visible when From field is in focus | Server started; From field is empty | Click into From field; enter text with leading spaces |
| t-15 | Verify leading spaces are deleted when From field loses focus | Server started; From field is empty | Click into From field; enter text with leading spaces; click outside to remove focus |
| t-16 | Verify trailing spaces remain visible when From field is in focus | Server started; From field is empty | Click into From field; enter text with trailing spaces |
| t-17 | Verify trailing spaces are deleted when From field loses focus | Server started; From field is empty | Click into From field; enter text with trailing spaces; click outside to remove focus |
| t-18 | Verify behavior when From field contains only spaces | Server started; From field is empty | Enter only spaces in the From field; click outside to remove focus |
| t-19 | Verify the user can enter spaces in To address field | Server started; To field is empty | Enter an address with spaces in the To field |
| t-20 | Verify the user can enter dashes in To address field | Server started; To field is empty | Enter an address with a dash in the To field |
| t-21 | Verify the user can enter periods in To address field | Server started; To field is empty | Enter an address with a period in the To field |
| t-22 | Verify the user can enter commas in To address field | Server started; To field is empty | Enter an address with a comma in the To field |
| t-23 | Verify the user can enter Latin characters in To address field | Server started; To field is empty | Enter Latin characters in the To field |
| t-24 | Verify error when entering non-Latin characters in To field | Server started; To field is empty | Enter non-Latin characters in the To field |
| t-25 | Verify error when entering special characters in To field | Server started; To field is empty | Enter special characters in the To field |
| t-26 | Verify behavior when To field is empty (0 characters) | Server started; To field is empty | Attempt to submit or validate an empty To field |
| t-27 | Verify valid minimum boundary of 1 character in To field | Server started; To field is empty | Enter exactly 1 allowed character in the To field |
| t-28 | Verify validation at 49 characters in To field | Server started; To field is empty | Enter a 49-character valid string in the To field |
| t-29 | Verify validation at maximum boundary of 50 characters in To field | Server started; To field is empty | Enter a 50-character valid string in the To field |
| t-30 | Verify error at first invalid boundary of 51 characters in To field | Server started; To field is empty | Enter a 51-character string in the To field |
| t-31 | Verify error when input exceeds length drastically in To field | Server started; To field is empty | Enter a 53-character string in the To field |
| t-32 | Verify leading spaces remain visible when To field is in focus | Server started; To field is empty | Click into To field; enter text with leading spaces |
| t-33 | Verify leading spaces are deleted when To field loses focus | Server started; To field is empty | Click into To field; enter text with leading spaces; click outside to remove focus |
| t-34 | Verify trailing spaces remain visible when To field is in focus | Server started; To field is empty | Click into To field; enter text with trailing spaces |
| t-35 | Verify trailing spaces are deleted when To field loses focus | Server started; To field is empty | Click into To field; enter text with trailing spaces; click outside to remove focus |
| t-36 | Verify behavior when To field contains only spaces | Server started; To field is empty | Enter only spaces in the To field; click outside to remove focus |

---

## Test Execution Results

| ID | Test Technique | Test Data | Expected Result | Actual Result | Status | Environment |
|---|---|---|---|---|---|---|
| example | Positive | `East 2nd Street, 601` | Numbers accepted in To field | Numbers are accepted in the To address field | **Pass** | Chrome 148.0.7778.217 (64-bit) |
| example | Positive | `1300 1st Street` | Numbers accepted in From field | Numbers are accepted in the From address field | **Pass** | Chrome 148.0.7778.217 (64-bit) |
| t-1 | Positive | `123 Creston Street` | Spaces accepted in From field | Spaces are not accepted in the From address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-2 | Positive | `123-B Creston Street` | Dashes accepted in From field | Dashes are not accepted in the From address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-3 | Positive | `123 Creston Street.` | Periods accepted in From field | Periods are not accepted in the From address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-4 | Positive | `123 Creston Street, Kalamazoo` | Commas accepted in From field | Commas are not accepted in the From address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-5 | Positive | `123 Creston Street` | Latin characters accepted in From field | Latin characters are not accepted in the From address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-6 | Negative | `123 Крестон Стрит` | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-7 | Negative | `#123 Creston Street` | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-8 | Negative | `""` | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-9 | Positive | `A` | 1-character address accepted | The 1-character address is not accepted | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-10 | Positive | `123 Creston Street, Kalamazoo, Michigan, MI, 4900` (49) | 49-character address accepted | The 49-character address is not accepted | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-11 | Positive | `123 Creston Street, Kalamazoo, Michigan, MI, 49002` (50) | 50-character address accepted | The 50-character address is not accepted | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-12 | Negative | `123 Creston Street, Kalamazoo, Michigan, MI, 49002-` (51) | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-13 | Negative | `123 Creston Street, Kalamazoo, Michigan, MI, 49002----` (53) | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-14 | Positive | `" 123 Creston Street"` | Leading spaces visible while in focus | Leading spaces remain visible while the field is in focus | **Pass** | Chrome 148.0.7778.217 (64-bit) |
| t-15 | Positive | `" 123 Creston Street"` | Leading spaces deleted on blur | Leading spaces are not automatically deleted when not in focus | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-16 | Positive | `"123 Creston Street "` | Trailing spaces visible while in focus | Trailing spaces remain visible while the field is in focus | **Pass** | Chrome 148.0.7778.217 (64-bit) |
| t-17 | Positive | `"123 Creston Street "` | Trailing spaces deleted on blur | Trailing spaces are not automatically deleted when not in focus | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-18 | Negative | `" "` | System trims spaces; field treated as empty / triggers error | System does not trim spaces, does not recognize field as empty | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-19 | Positive | `123 Creston Street` | Spaces accepted in To field | Spaces are not accepted in the To address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-20 | Positive | `123-B Creston Street` | Dashes accepted in To field | Dashes are not accepted in the To address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-21 | Positive | `123 Creston Street.` | Periods accepted in To field | Periods are not accepted in the To address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-22 | Positive | `123 Creston Street, Kalamazoo` | Commas accepted in To field | Commas are not accepted in the To address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-23 | Positive | `123 Creston Street` | Latin characters accepted in To field | Latin characters are not accepted in the To address field | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-24 | Negative | `123 Крестон Стрит` | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-25 | Negative | `#123 Creston Street` | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-26 | Negative | `""` | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-27 | Positive | `A` | 1-character address accepted | The 1-character address is not accepted | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-28 | Positive | `123 Creston Street, Kalamazoo, Michigan, MI, 4900` (49) | 49-character address accepted | The 49-character address is not accepted | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-29 | Positive | `123 Creston Street, Kalamazoo, Michigan, MI, 49002` (50) | 50-character address accepted | The 50-character address is not accepted | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-30 | Negative | `123 Creston Street, Kalamazoo, Michigan, MI, 49002-` (51) | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-31 | Negative | `123 Creston Street, Kalamazoo, Michigan, MI, 49002----` (53) | Displays "Incorrect address." | Error message not displayed | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-32 | Positive | `" 123 Creston Street"` | Leading spaces visible while in focus | Leading spaces remain visible while the field is in focus | **Pass** | Chrome 148.0.7778.217 (64-bit) |
| t-33 | Positive | `" 123 Creston Street"` | Leading spaces deleted on blur | Leading spaces are not automatically deleted when not in focus | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-34 | Positive | `"123 Creston Street "` | Trailing spaces visible while in focus | Trailing spaces remain visible while the field is in focus | **Pass** | Chrome 148.0.7778.217 (64-bit) |
| t-35 | Positive | `"123 Creston Street "` | Trailing spaces deleted on blur | Trailing spaces are not automatically deleted when not in focus | **Fail** | Chrome 148.0.7778.217 (64-bit) |
| t-36 | Negative | `" "` | System trims spaces; field treated as empty / triggers error | System does not trim spaces, does not recognize field as empty | **Fail** | Chrome 148.0.7778.217 (64-bit) |

---

## Report

| Value | Count | % |
|---|---|---|
| Number of Test Cases | 35 | 100% |
| Number of Passes | 5 | 14% |
| Number of Fails | 30 | 86% |

---

*Document: Project 2 EC, BV, TC — Project Version: v3.0*
