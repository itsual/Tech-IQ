# Tech IQ #20: AI Governance — What the Board Should Own vs. Delegate
*Accountability Doesn't Disappear Because a Model Made the Decision*

When an AI system denies a loan, misdiagnoses a document, or makes a discriminatory recommendation — the board cannot say "the algorithm decided." Legal liability, regulatory exposure, and reputational risk land on human shoulders regardless of what made the call.

This edition gives boards and CXOs a clear framework for what to own, what to delegate, and what to never outsource.

---

## Why Governance Matters Now — Not Later

```mermaid
timeline
    title The AI Regulatory Tightening Timeline
    2018 : GDPR (EU)
         : Right to explanation for automated decisions
         : First major regulation touching AI outputs
    2021 : EU AI Act Proposed
         : Risk-based framework for AI systems
         : High-risk categories defined
    2023 : US Executive Order on AI
         : Federal agencies must assess AI risks
         : Safety and transparency requirements
    2024 : EU AI Act Passed
         : World's first comprehensive AI law
         : Compliance required by 2026
    2025 : India DPDP Act enforcement begins
         : Personal data in AI training regulated
         : Consent frameworks required
    2026 : Global enforcement wave
         : Fines, audits, mandatory disclosures
         : Board-level accountability crystallizes
```

The window for "we'll figure out governance later" has closed. Boards that treat AI governance as an IT problem — not a fiduciary one — are accumulating undisclosed liability.

---

## The Governance Stack: Three Layers

```mermaid
flowchart TB
    subgraph Board["Board & CXO Layer — Own This"]
        B1[Risk appetite for AI\nWhat harms are unacceptable?]
        B2[Accountability structure\nWho is liable when AI causes harm?]
        B3[Regulatory posture\nAre we compliant with EU AI Act, DPDP, sector rules?]
        B4[Ethics boundaries\nWhat will we never automate — regardless of ROI?]
    end

    subgraph Exec["Executive / Leadership Layer — Set Policy"]
        E1[AI use case registry\nInventory of all deployed AI systems]
        E2[Risk classification\nHigh / Medium / Low risk per system]
        E3[Incident response\nWhat happens when AI causes harm]
        E4[Third-party AI governance\nVendors who use AI on your behalf]
    end

    subgraph Ops["Operational / Technical Layer — Execute & Monitor"]
        O1[Model cards and documentation]
        O2[Bias audits and fairness testing]
        O3[Explainability mechanisms]
        O4[Monitoring and drift detection]
        O5[Human-in-the-loop workflows]
        O6[Access controls and audit logs]
    end

    Board --> Exec --> Ops

    classDef board fill:#4285F4,stroke:#333,color:white;
    classDef exec fill:#34A853,stroke:#333,color:white;
    classDef ops fill:#e1f5fe,stroke:#4fc3f7;
    class B1,B2,B3,B4 board;
    class E1,E2,E3,E4 exec;
    class O1,O2,O3,O4,O5,O6 ops;
```

---

## What the Board Should Own — Non-Delegatable

These four decisions cannot be safely delegated to the AI team, the CTO, or a vendor. They require board-level clarity because they define the ethical and legal boundaries within which all other AI decisions are made.

### 1. Risk Appetite Statement

```mermaid
flowchart LR
    subgraph Questions["Board Must Answer"]
        Q1["In which decisions will AI\nnever have final say\nwithout human review?"]
        Q2["What is the maximum tolerable\nerror rate for each AI use case?"]
        Q3["What categories of data\nwill we never use to train AI?"]
        Q4["Under what circumstances\nwill we shut down an AI system?"]
    end

    subgraph Examples["Examples of Risk Appetite Decisions"]
        E1["'AI may recommend, but a human\nmust approve all credit decisions\nabove ₹50 lakh'"]
        E2["'We will not use inferred\nreligion, caste, or political views\nin any AI model — ever'"]
        E3["'If model accuracy drops below 85%\nthe system is taken offline\nautomatically'"]
    end

    classDef question fill:#e1f5fe,stroke:#4fc3f7;
    classDef example fill:#e8f5e9,stroke:#66bb6a;
    class Q1,Q2,Q3,Q4 question;
    class E1,E2,E3 example;
```

### 2. Accountability Structure

```mermaid
flowchart TD
    Harm([AI System Causes Harm\ne.g., discriminatory outcome\ncustomer financial loss\noperational disruption]) --> Q{Who is accountable?}

    Q --> Legal[Legal Liability\nDirectors personally liable\nin some jurisdictions\nfor AI-caused consumer harm]
    Q --> Reg[Regulatory Accountability\nFines under GDPR, EU AI Act,\nDPDP Act flow to the organization]
    Q --> Rep[Reputational Accountability\nPublic trust damage lands\non executive leadership]

    Legal & Reg & Rep --> Board["Board Answer Required:\nWhich executive owns AI risk?\nIs it the CTO, CISO, CDO, or a new role?\nWhat escalation path reaches the board?"]

    classDef harm fill:#ffebee,stroke:#ef9a9a;
    classDef account fill:#fff8e1,stroke:#ffca28;
    classDef board fill:#4285F4,stroke:#333,color:white;
    class Harm harm;
    class Legal,Reg,Rep account;
    class Board board;
```

### 3. Ethics Boundaries — The "Never Automate" List

Regardless of technical feasibility or ROI, some decisions should retain human judgment. The board should define this list explicitly.

| Category | Example Decision | Why AI Alone Is Insufficient |
|----------|-----------------|------------------------------|
| **Employment** | Terminate an employee | Legal process, context, human dignity |
| **Healthcare** | Deny a treatment or coverage | Medical complexity, patient rights |
| **Credit (high-value)** | Deny a large loan without explanation | Regulatory right to explanation |
| **Legal** | Determine guilt or liability | Due process requirements |
| **Safety-critical** | Override a safety interlock | Physical harm potential |
| **Grievance** | Reject a legal complaint | Procedural fairness |

---

## What to Delegate — With Oversight Structures

These decisions should be owned by named executives with clear reporting lines to the board.

```mermaid
flowchart TB
    subgraph CDO["Chief Data Officer / CDO"]
        CDO1[AI use case registry\nInventory of all AI systems in production]
        CDO2[Data governance for AI\nConsent, PII, retention policies]
        CDO3[Data quality standards\nAI-readiness criteria for datasets]
    end

    subgraph CTO["CTO / Chief AI Officer"]
        CTO1[Model risk framework\nClassification, assessment, approval]
        CTO2[Technical standards\nExplainability, monitoring, rollback]
        CTO3[Third-party AI vendor assessment\nBefore any AI vendor contract is signed]
    end

    subgraph CISO["CISO"]
        CISO1[AI security policy\nPrompt injection, model theft, adversarial attacks]
        CISO2[Access control for AI systems\nWho can query, modify, retrain models]
        CISO3[Incident response for AI failures\nDetection, containment, disclosure]
    end

    subgraph CFO["CFO"]
        CFO1[AI investment governance\nTCO framework, ROI measurement]
        CFO2[Cost monitoring\nToken costs, compute, human oversight]
        CFO3[AI vendor contract review\nLiability, SLA, data ownership clauses]
    end

    classDef role fill:#e8eaf6,stroke:#9fa8da;
    class CDO,CDO1,CDO2,CDO3 role;
    class CTO,CTO1,CTO2,CTO3 role;
    class CISO,CISO1,CISO2,CISO3 role;
    class CFO,CFO1,CFO2,CFO3 role;
```

---

## The AI Use Case Registry — The Foundation of Governance

You cannot govern what you have not inventoried. Every organization deploying AI needs a use case registry.

```mermaid
flowchart LR
    Registry[(AI Use Case Registry)] --> Fields

    subgraph Fields["Required Fields per Use Case"]
        F1[System name & description]
        F2[Business owner — named individual]
        F3[Data inputs — sources, sensitivity, consent status]
        F4[Decision type — recommendation vs. autonomous action]
        F5[Risk classification — High / Medium / Low]
        F6[Human oversight mechanism]
        F7[Evaluation method and frequency]
        F8[Regulatory applicability]
        F9[Last audit date]
        F10[Incident history]
    end

    subgraph Trigger["What Triggers Registration"]
        T1[Any new AI system approved for production]
        T2[Any AI capability added to existing product]
        T3[Any third-party AI service integrated]
        T4[Any AI used to make or influence decisions\naffecting customers or employees]
    end

    classDef registry fill:#4285F4,stroke:#333,color:white;
    classDef field fill:#e1f5fe,stroke:#4fc3f7;
    classDef trigger fill:#fff8e1,stroke:#ffca28;
    class Registry registry;
    class F1,F2,F3,F4,F5,F6,F7,F8,F9,F10 field;
    class T1,T2,T3,T4 trigger;
```

---

## Risk Classification — The EU AI Act Framework Simplified

The EU AI Act classifies AI systems by risk level. This is the practical framework boards should apply regardless of jurisdiction — because customers and regulators expect it.

```mermaid
flowchart TD
    System([AI System]) --> Q1{Does it pose\nunacceptable risk?}
    Q1 --> |Yes| Prohibited["🚫 Prohibited\nNever deploy\n\nExamples:\n• Social scoring by government\n• Real-time biometric\n  mass surveillance\n• Emotion recognition\n  in workplace/school"]

    Q1 --> |No| Q2{High-risk domain?}
    Q2 --> |Yes| High["⚠️ High Risk\nStrict requirements before deployment\n\nDomains:\n• Credit scoring\n• Recruitment / HR decisions\n• Critical infrastructure\n• Law enforcement\n• Education assessment\n• Healthcare diagnostics\n\nRequired: conformity assessment,\nhuman oversight, transparency,\naccuracy documentation"]

    Q2 --> |No| Q3{Interacts with\nhumans / generates content?}
    Q3 --> |Yes| Limited["📋 Limited Risk\nTransparency obligations\n\nExamples:\n• Chatbots — must disclose AI\n• Deepfakes — must be labeled\n• Emotion recognition — must disclose"]

    Q3 --> |No| Minimal["✅ Minimal Risk\nNo mandatory requirements\nbut good practice applies\n\nExamples:\n• Spam filters\n• AI in video games\n• Inventory optimization"]

    classDef prohibited fill:#ffebee,stroke:#ef9a9a;
    classDef high fill:#fff8e1,stroke:#ffca28;
    classDef limited fill:#e1f5fe,stroke:#4fc3f7;
    classDef minimal fill:#e8f5e9,stroke:#66bb6a;
    class Prohibited prohibited;
    class High high;
    class Limited limited;
    class Minimal minimal;
```

---

## Explainability — A Practical Requirement, Not Just Ethics

For any AI system making decisions that affect people, the ability to explain the decision is both a legal right and a trust requirement.

```mermaid
flowchart LR
    subgraph Types["Levels of Explainability"]
        L1["Global Explainability\n'Which factors matter most\nfor this model overall?'\nExample: Feature importance charts"]
        L2["Local Explainability\n'Why did the model make\nthis specific decision for this person?'\nExample: SHAP values, LIME"]
        L3["Counterfactual Explanation\n'What would have to change\nfor the decision to be different?'\nExample: If your income were 20% higher,\nthe loan would be approved'"]
    end

    subgraph Tools["Practical Tools"]
        T1[SHAP — model-agnostic\nfeature attribution]
        T2[LIME — local approximation\nfor complex models]
        T3[Integrated Gradients\nfor neural networks]
        T4[Natural language explanation\ngenerated by LLM from model output]
    end

    classDef level fill:#e8eaf6,stroke:#9fa8da;
    classDef tool fill:#e8f5e9,stroke:#66bb6a;
    class L1,L2,L3 level;
    class T1,T2,T3,T4 tool;
```

**Board Question**: For every high-risk AI system, can we produce a written explanation for any individual decision within 24 hours? Under GDPR and the EU AI Act, this is a legal requirement for automated decisions affecting people.

---

## The AI Incident Response Plan

Every organization with AI in production needs a defined response plan for AI-caused incidents — before the incident happens.

```mermaid
flowchart TD
    Incident([AI Incident Detected\ne.g., mass wrong decisions,\ndata leak via prompt,\ndiscriminatory outcomes]) --> Triage

    subgraph Response["Incident Response Flow"]
        Triage[Triage: Severity Assessment\nP1 — regulatory breach / customer harm\nP2 — quality degradation\nP3 — operational issue]
        Contain[Containment\nKill switch / rollback\nwithin defined SLA]
        Assess[Impact Assessment\nHow many affected?\nWhat decisions were wrong?\nRegulatory notification required?]
        Notify[Notification\nInternal: Board within 24h for P1\nRegulatory: GDPR 72h window\nCustomer: as required by law]
        RCA[Root Cause Analysis\nData issue? Model issue?\nPrompt injection? Process failure?]
        Remediate[Remediation\nFix + reprocess affected decisions\nCompensate affected parties\nUpdate model/process/guardrails]
        Learn[Post-Incident Review\nUpdate governance framework\nCommunicate lessons learned]
    end

    Triage --> Contain --> Assess --> Notify --> RCA --> Remediate --> Learn

    classDef incident fill:#ffebee,stroke:#ef9a9a;
    classDef step fill:#e1f5fe,stroke:#4fc3f7;
    class Incident incident;
    class Triage,Contain,Assess,Notify,RCA,Remediate,Learn step;
```

---

## The Board AI Governance Checklist

| Governance Element | Status | Owner | Review Frequency |
|-------------------|--------|-------|-----------------|
| AI risk appetite statement documented | ⬜ | Board | Annual |
| Named executive accountable for AI risk | ⬜ | CEO | Permanent |
| AI use case registry maintained | ⬜ | CDO | Quarterly |
| All AI systems risk-classified | ⬜ | CTO / CDO | Per new deployment |
| High-risk systems: conformity assessment done | ⬜ | CTO | Per deployment |
| Explainability mechanism in place for customer-facing AI | ⬜ | CTO | Per deployment |
| AI incident response plan documented & tested | ⬜ | CISO | Annual drill |
| Third-party AI vendor contracts reviewed for liability | ⬜ | CFO / Legal | Per contract |
| Employee AI use policy published | ⬜ | CHRO | Annual |
| Board briefed on AI risk quarterly | ⬜ | CTO / CDO | Quarterly |

---

## Key Takeaways

1. **AI governance is a board responsibility, not a technical one.** The board sets the risk appetite. Everything else follows from that. If the board has not set it, no one else can.
2. **"The algorithm decided" is not a legal defense.** Directors carry personal liability in some jurisdictions for AI-caused consumer harm. Know this before the incident.
3. **The EU AI Act is not optional for global companies.** If your AI touches EU residents — as customers, employees, or partners — you are in scope. The enforcement wave is here.
4. **Inventory before governance.** You cannot classify, monitor, or govern AI systems you have not catalogued. A use case registry is the first governance deliverable.
5. **Explainability is a product requirement for high-risk AI.** Not because regulators demand it — because customers expect it and trust requires it.

---

Simplifying tech for decisive leadership. Connect with me on [LinkedIn](https://www.linkedin.com/in/arockialiborious/) for real-talk AI insights.
