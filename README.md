# Contribution [#27940]: [React Doctor] no-uncontrolled-input

**Contribution Number:** [1]  
**Student:** Kushi Kumbagowdana 
**Issue:** https://github.com/wso2/product-is/issues/27940
**Status:** [Phase 2]

---

## Why I Chose This Issue

I chose this issue as it deals with noticing minor details and understanding React concepts on a deeper level which is something I want to work on and strengthen in my skill set. I hope to learn why these functions are needed and how we can notice when they are in need of fixing. Keeping an eye on small details as such, are what helps us grow as a software engineer and turns products from good to great. 

---

## Understanding the Issue

### Problem Description

For this issue, there are multiple files that have input elemnets that React thinks are controlled, however they are not, and there is no way to update their value.

### Expected Behavior

The expected behavior is that every input field should behave as either a controlled input or an uncontrolled input.

### Current Behavior

The inputs look editable while they are actually being read-only, where nothing happens and warnings appear.

### Affected Components

There are 12 files affectd:
admin.branding.v1/components/preview/sign-in-box/fragments/email-otp-fragment.tsx:64
admin.branding.v1/components/preview/sign-in-box/fragments/push-auth-fragment.tsx:60
admin.branding.v1/components/preview/sign-in-box/fragments/password-reset-fragment.tsx:57
admin.branding.v1/components/preview/sign-in-box/fragments/password-reset-fragment.tsx:205
admin.branding.v1/components/preview/sign-in-box/fragments/totp-fragment.tsx:117
admin.branding.v1/components/preview/sign-in-box/fragments/sms-otp-fragment.tsx:113
admin.branding.v1/components/preview/sign-in-box/fragments/sign-up-fragment.tsx:61
admin.branding.v1/components/preview/sign-in-box/fragments/sign-up-fragment.tsx:98
admin.branding.v1/components/preview/sign-in-box/fragments/sign-up-fragment.tsx:125
admin.logs.v1/pages/diagnostic-logs-page.tsx:373
admin.logs.v1/pages/audit-logs-page.tsx:373
admin.policy-administration.v1/components/policy-administration-page-layout.tsx:326

---

## Reproduction Process

### Environment Setup

[Notes on setting up your local development environment - challenges you faced, how you solved them]
- I was a bit confused on whether I should work with the tags or through a branch, but was able to solve this by communictaing with maintainer and came to conclusion of working on latest branch.

### Steps to Reproduce

1. Fork the repository
2. Clone onto local machine
3. Set your working directory by setting up appropriate branch using checkout command
4. Build the product with Maven using their setup https://wso2.github.io/using-maven.html
5. Update files as needed
6. Upstream repository with your local branch

### Reproduction Evidence

- **Commit showing reproduction:** https://github.com/kkushi7/identity-apps/tree/feature/email-opt-fragment
- **Screenshots/logs:** [If applicable]
- **My findings:** [What you discovered during reproduction]

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]
This issue is caused by a React lint rule as React think the input elements are controlled when they do not have a way to update their values.

### Proposed Solution

[High-level description of your fix approach]
My proposed approach is to go to each file, and thankfully each line where the issue occurs is stated, and understand based on its missing attributes. 

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** The React input elements are perceived as controlled, when in fact they are not as there is no way to update their values and become classified as read-only. 

**Match:** [What similar patterns/solutions exist in the codebase?] Within the codebase there is the pattern of onChange and useStates which shows how we should deal with the uncontrolled inputs as they are missing these attributes. 

**Plan:** [Step-by-step implementation plan]
1. Modify each file listed with error at line stated
2. Add proper functions as needed to make inputs controlled
3. Run tests to check working functions

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** [How will you verify it works?]

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- https://wso2.github.io/
- https://github.com/wso2/product-is/blob/master/docs/CONTRIBUTING.md
- [GitHub issues or discussions that helped]
