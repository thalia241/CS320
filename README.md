# CS-320 Portfolio Submission

## Included Artifacts
- **Contact Service (Project One)**: `Contact.java`, `ContactService.java`, `ContactTest.java`, `ContactServiceTest.java`
- **Summary & Reflections (Project Two)**: `CS320Project_Two_Deel.docx`

---

## Reflection

### 1) How can I ensure that my code, program, or software is functional and secure?
I enforce requirements up front (defensive validation) and confirm behaviors with focused **JUnit unit tests** and **negative tests** that target edge cases and invalid inputs. Examples include rejecting non-10-digit phone numbers, blocking duplicate IDs across services, and disallowing appointments with past dates. Tests cover both success and failure paths, with setup consolidated via `@BeforeEach` to keep suites maintainable. This approach hardens inputs (fail-closed), preserves data integrity, and provides fast feedback that prevents regressions.

### 2) How do I interpret user needs and incorporate them into a program?
I translate stated requirements into **concrete, testable acceptance criteria** embedded in both code and tests. For instance:
- *Contacts*: unique ID, first/last name, 10-digit phone, non-empty address.
- *Tasks*: unique ID, non-empty name, bounded description length.
- *Appointments*: unique ID, non-empty description, **future** date only.
Each rule is implemented in the domain model/service and proven with unit tests that assert both valid behavior and explicit exceptions for violations. This tight spec-to-test mapping keeps features aligned with stakeholder expectations.

### 3) How do I approach designing software?
I use a **modular, service-oriented** design with clear separation of concerns:
- Plain data models (`Contact`, `Task`, `Appointment`)
- Thin services (`ContactService`, `TaskService`, `AppointmentService`) that own business rules and identity constraints
- Small, explicit APIs for add/update/get/delete
I pair this with disciplined testing (including boundary and time-based checks), which drives simpler interfaces and improves evolvability. Integration and persistence are identified as next steps once unit behavior is solid.
