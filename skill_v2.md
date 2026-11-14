# Test Case Generation Skill

## Objective

Generate complete, requirement-based manual test cases for the supplied
product requirements, including any relevant diagrams. Test cases must
provide sufficient coverage without inventing behaviour that is not
defined by the requirement.

## Test Case Count and Coverage Rules

1.  Create **one primary test case for each requirement**. This test
    case must cover the complete happy path and all applicable positive
    behaviour explicitly described in the requirement.
2.  Add an **optional second test case** only when a meaningful negative
    scenario or edge case needs separate validation.
3.  Add a **third test case only when another distinct scenario is
    necessary** to achieve complete requirement coverage.
4.  Do not create multiple test cases merely to split a requirement into
    smaller pieces. Prefer a single comprehensive happy-path test case
    when it can clearly and practically cover the requirement.
5.  Do not omit any scenario that is explicitly stated or necessarily
    implied by the requirement. Avoid duplicate or redundant scenarios.

## Test Summary Naming Convention

Use the following format exactly:

-   `TC1 CPPEL-1234 <one-line description of what is being tested> - happy path case`
-   `TC2 CPPEL-1234 <one-line description of what is being tested> - negative / edge case`
-   `TC3 CPPEL-1234 <one-line description of what is being tested> - any other case`

Replace `CPPEL-1234` with the actual requirement or Jira ID supplied by
the user. Keep each description concise, specific, and traceable to the
requirement.

Use only the summaries that apply. Do not add a TC2 or TC3 when no
additional distinct test is required.

## Test Case Structure

For every test case, provide: - **Test Summary** - **Test Steps** -
**Expected Results**

The **first test step must always be the Precondition**. Start the first
step with `Precondition:` and include the required setup, configuration,
user permissions, application state, test data, and/or connected
equipment needed to execute the test.

Write test steps and expected results side by side in separate columns
so they can be copied into Excel or Jira.

Each step must describe a clear, executable action. Each expected result
must state the observable outcome for that corresponding step. Keep the
steps in execution order and avoid combining unrelated actions.

## Requirement Analysis and Coverage

Before writing test cases: 1. Read the entire requirement carefully,
including its title, description, acceptance criteria, notes, referenced
requirements, and supplied diagrams. 2. Identify the user flow,
applicable conditions, inputs, configuration choices, validations,
outputs, state changes, and relevant boundaries. 3. If a diagram exists,
analyse it as an additional source of behaviour. Use it to identify
flows, decision points, alternate paths, relationships, transitions, and
scenarios that may not be obvious from the text alone. 4. Map the
identified scenarios to the proposed test steps and expected results.
Ensure that the requirement is completely covered. 5. Include only
behaviour supported by the requirement, diagram, or other context
explicitly supplied by the user.

## Handling Unclear or Incomplete Requirements

**Do not fabricate expected behaviour.**

If any part of the requirement is ambiguous, incomplete, contradictory,
or missing information needed to define a reliable test: 1. Stop and
identify the exact ambiguity or missing detail. 2. Ask the user a clear,
specific question. 3. Do not assume product behaviour or write an
expected result based on guesswork. 4. Once the user clarifies, use that
clarification when preparing the test cases.

If the ambiguity affects only one scenario, you may prepare the clearly
defined coverage separately, but clearly identify the unresolved point
and do not invent its expected result.

## Output Quality Rules

-   Ensure every test case is directly traceable to the supplied
    requirement and its Jira ID.
-   Use clear, professional, simple language.
-   Use consistent terminology from the requirement and product UI.
-   Make expected results specific, observable, and verifiable.
-   Cover the complete happy path in TC1.
-   Add negative, edge, or other test cases only when they add distinct
    and necessary coverage.
-   Do not assume UI labels, messages, default values, permissions,
    limits, or system responses that are not specified.
-   Do not add unrelated tests or expand the scope beyond the supplied
    requirement.
-   If a diagram conflicts with the written requirement, flag the
    conflict and ask the user which source should take precedence.

## Final Review Before Responding

Verify that: - TC1 covers the complete happy path. - Any necessary
negative or edge cases are included without duplication. - The first
step of every test case is `Precondition:`. - Every action has a
corresponding expected result. - All stated requirement scenarios and
relevant diagram flows are covered. - No expected behaviour has been
fabricated. - Any unresolved ambiguity is raised as a question rather
than silently assumed.
