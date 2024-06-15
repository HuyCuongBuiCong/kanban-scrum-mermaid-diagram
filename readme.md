# Understanding Kanban and Scrum with Mermaid Diagrams for Beginners 

## Scrum

### What is Scrum

```mermaid
mindmap
  root((Scrum))
    root --> A["What is Scrum?"]
        A --> A1["Agile framework for managing complex projects"]
        A --> A2["Iterative cycles called sprints"]
            A2 --> A2a["Typically lasting 2-4 weeks"]
            A2 --> A2b["Teams work on prioritized tasks"]
    root --> B["Key Events"]
        B --> B1["Sprint Planning"]
        B --> B2["Daily Scrum"]
        B --> B3["Sprint Review"]
        B --> B4["Sprint Retrospective"]
    root --> C["Emphasizes"]
        C --> C1["Collaboration"]
        C --> C2["Flexibility"]
        C --> C3["Continuous improvement"]
    root --> D["Goal"]
        D --> D1["Deliver high-quality results"]

```

### Scrum Workflow

```mermaid
stateDiagram-v2
    [*] --> ProductBacklog
    ProductBacklog --> SprintPlanning: Prioritize Backlog
    SprintPlanning --> Sprint: Define Sprint Goal
    Sprint --> DailyScrum: Start Sprint
    DailyScrum --> DailyScrum: Daily Stand-up
    DailyScrum --> SprintReview: End of Sprint
    SprintReview --> SprintRetrospective: Review Increment
    SprintRetrospective --> SprintPlanning: Reflect and Improve
    SprintRetrospective --> [*]: Plan Next Sprint

    state ProductBacklog {
        [*] --> BacklogItems
        BacklogItems --> [*]
    }

    state Sprint {
        [*] --> DevelopmentWork
        DevelopmentWork --> [*]
    }
```

```mermaid
sequenceDiagram
    participant PO as Product Owner
    participant SM as Scrum Master
    participant DT as Development Team
    participant SH as Stakeholder

    PO->>+PO: Create Product Backlog
    PO->>+PO: Prioritize Backlog
    PO->>+SM: Request Sprint Planning
    SM->>+DT: Facilitate Sprint Planning
    note right of DT: Define sprint goal and select backlog items
    SM->>DT: Conduct Daily Scrum
    note right of DT: Daily stand-up meetings to discuss progress and obstacles
    DT->>+DT: Development Work
    note right of DT: Team works on sprint tasks
    DT-->>DT: Update Sprint Backlog
    SM->>+DT: Facilitate Sprint Review
    DT->>+SH: Demonstrate Increment
    SH->>+DT: Provide Feedback
    DT->>+PO: Receive Feedback
    SM->>+DT: Facilitate Sprint Retrospective
    note right of DT: Reflect on sprint and identify improvements
    DT->>+SM: Plan Next Sprint
    note right of DT: Prepare for the next sprint cycle
```


### Sprint Cycle

```mermaid
gantt
    title Scrum Sprint Cycle
    dateFormat  YYYY-MM-DD
    section Sprint Preparation
    Create Product Backlog       :done, 2024-06-01, 2d
    Prioritize Backlog           :done, 2024-06-03, 1d

    section Sprint
    Sprint Planning              :active, 2024-06-04, 4h 
    Development Work             :2024-06-05, 2024-06-14
        Task 1                   :2024-06-05, 2024-06-07
        Task 2                   :2024-06-07, 2024-06-10
        Task 3                   :2024-06-10, 2024-06-14
        Code Review              :2024-06-07, 2024-06-08
        Integration Testing      :2024-06-11, 2024-06-12
        Bug Fixing               :2024-06-13, 2024-06-14
    Daily Scrum                  :2024-06-05, 15m
    Daily Scrum                  :2024-06-06, 15m
    Daily Scrum                  :2024-06-07, 15m
    Daily Scrum                  :2024-06-08, 15m
    Daily Scrum                  :2024-06-09, 15m
    Daily Scrum                  :2024-06-10, 15m
    Daily Scrum                  :2024-06-11, 15m
    Daily Scrum                  :2024-06-12, 15m
    Daily Scrum                  :2024-06-13, 15m
    Daily Scrum                  :2024-06-14, 15m
    Sprint Review                :2024-06-15, 1d
    Sprint Retrospective         :2024-06-16, 1d

    section Continuous Improvement
    Apply Feedback               :2024-06-17, 2d
    Plan Next Sprint             :2024-06-19, 4h
```

### Srum Board

```mermaid
flowchart TD
    subgraph Backlog["Backlog (To Do)"]
        A1["Task 1"]
        A2["Task 2"]
        A3["Task 3"]
    end

    subgraph InProgress["In Progress"]
        B1["Task 4"]
        B2["Task 5"]
    end

    subgraph InReview["In Review/Testing"]
        C1["Task 6"]
        C2["Task 7"]
    end

    subgraph Done["Done"]
        D1["Task 8"]
        D2["Task 9"]
    end

    Backlog --> InProgress
    InProgress --> InReview
    InReview --> Done
```
#### Sample Scrum Board

```mermaid
flowchart TD
    subgraph ToDo["To Do"]
        direction TB
        B1["Task: Create wireframes (User Story 1)"]
        C1["Task: Research best practices (User Story 2)"]
        D1["Task: Compress images (User Story 3)"]
    end

    subgraph InProgress["In Progress"]
        direction TB
        B2["Task: Design homepage layout (User Story 1)"]
        C2["Task: Design new navigation menu (User Story 2)"]
    end

    subgraph InReview["In Review"]
        direction TB
        B3["Task: Implement homepage in HTML/CSS (User Story 1)"]
        D2["Task: Implement lazy loading (User Story 3)"]
    end

    subgraph Done["Done"]
        direction TB
        C3["Task: Implement navigation in HTML/CSS (User Story 2)"]
    end

    ToDo --> InProgress
    InProgress --> InReview
    InReview --> Done
```

## Kanban

### What is Kanban

```mermaid
mindmap
  root((Kanban))

    root --> A["What is Kanban?"]
        A --> A1["Visual workflow management method"]
        A --> A2["Focuses on continuous delivery"]
        A --> A3["Avoids overburdening the team"]

    root --> B["How Kanban Works"]
        B --> B1["Uses a board with columns"]
            B1 --> B1a["Columns represent stages of the process"]
            B1 --> B1b["Tasks move through these stages"]

    root --> C["Key Principles"]
        C --> C1["Visualizing work"]
        C --> C2["Limiting Work in Progress (WIP)"]
        C --> C3["Continuously improving flow"]

    root --> D["Benefits"]
        D --> D1["Manage tasks efficiently"]
        D --> D2["Respond to changes quickly"]

```

## Kanban Workflow

```mermaid
sequenceDiagram
    participant TM as Team Member
    participant PM as Project Manager
    participant SH as Stakeholder

    PM->>+TM: Design Workflow
    note right of TM: Understand the process
    TM->>+TM: Create Kanban Board
    note right of TM: Visualize work
    TM->>+PM: Propose WIP Limits
    PM->>+TM: Agree on WIP Limits
    TM->>+TM: Pull Work
    note right of TM: Pull work when ready
    loop Actively Manage Flow
    TM->>+TM: Monitor Work
    note right of TM: Track key metrics
    TM->>+TM: Fix Issues
    end
    TM->>+SH: Provide Updates
    SH->>+TM: Give Feedback
    TM->>+PM: Reflect and Improve (with Team)
    note right of TM: Analyze and adapt
    TM->>+PM: Apply Changes
    PM->>+TM: Repeat Process
```

### Kanban Board

```mermaid
flowchart TD
    subgraph Backlog["Backlog (To Do)"]
        A1["Task 1"]
        A2["Task 2"]
        A3["Task 3"]
    end

    subgraph ReadyForDev["Ready for Development"]
        B1["Task 4"]
    end

    subgraph InProgress["In Progress"]
        C1["Task 5"]
    end

    subgraph Blocked["Blocked"]
        D1["Task 6"]
    end

    subgraph InReview["In Review/Testing"]
        E1["Task 7"]
    end

    subgraph ReadyForRelease["Ready for Release"]
        F1["Task 8"]
    end

    subgraph Done["Done"]
        G1["Task 9"]
    end

    Backlog --> ReadyForDev
    ReadyForDev --> InProgress
    InProgress --> Blocked
    InProgress --> InReview
    Blocked --> InProgress
    InReview --> ReadyForRelease
    ReadyForRelease --> Done
```

#### Sample Kanban Board

```mermaid
flowchart TD
    subgraph Backlog
        A1["Project 54\nActivities search bar"]
        A2["Project 55\nCustomer support through Messenger"]
        A3["Project 56\nSMS confirmation 24h before departure"]
        A4["Project 57\niOS App"]
        A5["Project 58\nAndroid App"]
        A6["Project 59\nMaximum stop duration filter"]
    end

    subgraph Selected
        B1["Project 39\nFacebook SSO"]
        B2["Project 40\nAirline review"]
        B3["Project 41\nShuttle and transfer information"]
        B4["Project 42\nCar rental"]
    end

    subgraph ToSpecify
        direction TB
        C1["Project 36\nPrice alert feature"]
        C2["Project 37\nShow public holidays in local countries"]
        C3["Project 38\nHistorical flight activity (5 years back)"]
    end

    subgraph InDevelopment
        direction TB
        D1["Project 22\nAdapt cookies to GDPR"]
        D2["Project 29\nMulti-city flights"]
        D3["Project 30\nMeal selection"]
        D4["Project 31\nIntegrity of Air France data"]
    end

    subgraph ToTest
        direction TB
        E1["Project 32\nNumber of tickets left error"]
        E2["Project 33\nCurrency conversion"]
        E3["Project 34\nVaccine passport upload"]
    end

    subgraph ToDeploy
        direction TB
        F1["Project 21\nHotel search bar"]
        F2["Project 24\nPaypal integration"]
    end

    subgraph Done
        direction TB
        G1["Project 23\nGoogle SSO"]
        G2["Project 28\nSeat selection"]
    end

    Backlog --> Selected
    Selected --> ToSpecify
    ToSpecify --> InDevelopment
    InDevelopment --> ToTest
    ToTest --> ToDeploy
    ToDeploy --> Done

```

## Comparison between Scrum and Kanban

```mermaid
graph LR
  classDef bigText font-size:30px, padding:10px;
  
  A["Scrum vs Kanban"]:::bigText

  subgraph Similarities
    A1["Visual Management 📝"]:::bigText
    A2["Workflow Focus ⚙️"]:::bigText
    A3["Continuous Improvement 🔄"]:::bigText
    A4["Limit WIP 🚦"]:::bigText
  end

  subgraph Differences
    B1["Roles 👥"]:::bigText
    B2["Workflow 📈"]:::bigText
    B3["Events 📅"]:::bigText
    B4["Artifacts 📦"]:::bigText
    B5["Workflow Management 🛠️"]:::bigText
    B6["Framework 📜"]:::bigText
    B7["Story Points & Estimates 📊"]:::bigText
  end

  A --> Similarities:::bigText
  A --> Differences:::bigText

  A1 --> A1_1["Both use visual boards (Scrum board, Kanban board) to represent work items and their progress."]:::bigText
  A2 --> A2_1["Both focus on optimizing the flow of work through a system."]:::bigText
  A3 --> A3_1["Both emphasize regular reflection and adaptation to improve processes and outcomes."]:::bigText
  A4 --> A4_1["Both encourage limiting the amount of work in progress to prevent bottlenecks and improve efficiency."]:::bigText

  B1 --> B1_1["Scrum: Defined Roles (Product Owner, Scrum Master, Development Team)"]:::bigText
  B1 --> B1_2["Kanban: Flexible Roles (No prescribed roles)"]:::bigText
  B2 --> B2_1["Scrum: Timeboxed Iterations (Sprints, typically 2-4 weeks)"]:::bigText
  B2 --> B2_2["Kanban: Continuous Flow"]:::bigText
  B3 --> B3_1["Scrum: Regular Events (Sprint Planning, Daily Scrum, Sprint Review, Sprint Retrospective)"]:::bigText
  B3 --> B3_2["Kanban: Optional Events (Cadences)"]:::bigText
  B4 --> B4_1["Scrum: Specific Artifacts (Product Backlog, Sprint Backlog, Increment)"]:::bigText
  B4 --> B4_2["Kanban: Kanban Board & Metrics"]:::bigText
  B5 --> B5_1["Scrum: Push System (Planned Work)"]:::bigText
  B5 --> B5_2["Kanban: Pull System (On-Demand Work)"]:::bigText
  B6 --> B6_1["Scrum: Prescriptive Framework"]:::bigText
  B6 --> B6_2["Kanban: Flexible Framework"]:::bigText
  B7 --> B7_1["Scrum: Uses story points for estimating work."]:::bigText
  B7 --> B7_2["Kanban: Focuses on flow efficiency, may not use story points."]:::bigText
```

## Conclusion
Choosing between Scrum and Kanban depends on your team's needs and project requirements. Scrum is ideal for teams that prefer structured roles and timeboxed iterations, while Kanban offers more flexibility and continuous flow. Evaluate your team's workflow, goals, and preferences to decide which methodology best fits your project.