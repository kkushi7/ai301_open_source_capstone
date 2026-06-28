# Contribution [#27940]: [React Doctor] no-uncontrolled-input

**Contribution Number:** [1]  
**Student:** Kushi Kumbagowdana 
**Issue:** https://github.com/wso2/product-is/issues/27940
**Status:** [Phase 3]

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
- I got confused with which set up to do as there were many resoirces, but realized I only needed to do frontend set up which was eaiser to follow through their guide. 

### Steps to Reproduce

1. Fork the repository
2. Clone onto local machine
3. Download necessary frameworks and languages; Node.ja, Maven, pnpm, openJDK 21-23
4. Set your working directory by setting up appropriate branch using checkout command
5. Build the product with Maven using their setup https://wso2.github.io/using-maven.html
6. Upstream repository with your local branch

### Reproduction Evidence

- **Commit showing reproduction:** https://github.com/kkushi7/identity-apps/tree/feature/email-opt-fragment
- **Screenshots/logs:** [If applicable]
- **My findings:** Since this is a frontend issue, I did not need to set up backend which I got confused over and had to redo my set up.

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
2. Add proper functions as needed to make inputs controlled (ex: readOnly, useState(""), onChange)
3. Run linter to check working functions, since this is an linter issue

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** I will verify my work by running the targeted linter function as we are given the exact file and line where the issue occurs, so I am able to see right away whether I fixed the issue or not within those files. 

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

I plan on doing the tests manually using the linter function as this issue caused through the React lint so was able to do it for each file given using the target lint function: pnpm lint:targeted -- path/to/file.tsx

---

## Implementation Notes

### Week [5] Progress

[What you built this week, challenges faced, decisions made]
- I had to redo set up as I relaized I did the wrong one, which was for backend when my issue is frontend. Was able to figure it out thanks to the guide they provided.

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
- https://github.com/wso2/identity-apps/blob/b2a8f16f154cf4ada332b7d624ba4b0ad7629518/docs/DEVELOPER.md#setting-up-development-tools
- [GitHub issues or discussions that helped]
