# Team and Program Events in SAFe

## Scrum Events in SAFe Context

### 1. Sprint Planning
```markdown
Duration: 4 hours (2-week sprint)
Participants:
- Scrum Master
- Product Owner
- Development Team

Agenda:
1. Review Sprint Goals (30 mins)
   - Align with PI Objectives
   - Confirm team capacity
   - Review dependencies

2. Story Review (2 hours)
   - Acceptance criteria
   - Technical approach
   - Team commitments

3. Sprint Backlog Creation (1.5 hours)
   - Task breakdown
   - Effort estimation
   - Capacity allocation
```

### 2. Daily Stand-up
```python
# Example: Daily Stand-up Structure
class DailyStandUp:
    def __init__(self):
        self.timeboxed_minutes = 15
        self.key_questions = [
            "What did you complete yesterday?",
            "What will you work on today?",
            "Any impediments?"
        ]
        
    def run_meeting(self, team_members):
        for member in team_members:
            self.answer_questions(member)
            self.check_dependencies()
            self.update_board()
            
    def identify_impediments(self):
        return {
            'technical': [],
            'process': [],
            'dependencies': []
        }
```

### 3. Iteration Review
```markdown
Structure (2-hour timebox):
1. Business Context (15 mins)
   - Market updates
   - Customer feedback
   - Strategic alignment

2. Demo Preparation (30 mins)
   - Setup environments
   - Data preparation
   - Rehearsal

3. Demonstration (45 mins)
   - Feature showcase
   - User story completion
   - Technical achievements

4. Feedback Collection (30 mins)
   - Stakeholder input
   - Improvement suggestions
   - Next steps
```

### 4. Retrospective
```javascript
// Example: Retrospective Tool
const retrospectiveTool = {
  categories: {
    went_well: [],
    needs_improvement: [],
    action_items: []
  },
  
  addItem(category, item) {
    this.categories[category].push({
      description: item,
      votes: 0,
      actionable: false
    });
  },
  
  generateActionPlan() {
    return this.categories.action_items.map(item => ({
      action: item.description,
      owner: assignOwner(),
      deadline: setDeadline(),
      status: 'Open'
    }));
  }
};
```

## Kanban vs. Scrum in SAFe

### Kanban Implementation
```markdown
Board Structure:
| Backlog | Analysis | Development | Testing | Done |
|---------|----------|-------------|---------|------|
| WIP: ∞  | WIP: 3   | WIP: 5     | WIP: 3  | WIP: ∞ |

Policies:
1. Pull System
   - Only pull when capacity available
   - Respect WIP limits
   - Complete definition of done

2. Flow Metrics
   - Lead Time
   - Cycle Time
   - Throughput
   - Quality metrics
```

### Scrum Implementation
```markdown
Sprint Structure:
1. Sprint Planning
   - Capacity planning
   - Story point commitment
   - Sprint goal setting

2. Sprint Execution
   - Daily stand-ups
   - Story completion
   - Burndown tracking

3. Sprint Review
   - Demo completed work
   - Gather feedback
   - Update backlog

4. Sprint Retrospective
   - Team improvement
   - Process adjustment
   - Action items
```

## Planning and Executing the Iteration

### 1. Iteration Planning
```python
# Example: Iteration Planning Calculator
class IterationPlanner:
    def __init__(self):
        self.team_capacity = 0
        self.story_points = []
        self.dependencies = []
        
    def calculate_capacity(self, team_members, working_days):
        return sum([
            member.availability * working_days * member.velocity
            for member in team_members
        ])
        
    def plan_iteration(self, backlog_items):
        planned_items = []
        current_capacity = self.team_capacity
        
        for item in backlog_items:
            if self.can_accommodate(item, current_capacity):
                planned_items.append(item)
                current_capacity -= item.points
                
        return planned_items
```

### 2. Backlog Refinement
```markdown
Refinement Process:
1. Story Preparation
   - User story writing
   - Acceptance criteria
   - Dependencies identified

2. Estimation
   - Planning poker
   - Team discussion
   - Complexity assessment

3. Prioritization
   - Business value
   - Technical risk
   - Dependencies

4. Ready for Sprint
   - INVEST criteria met
   - Team understood
   - Sized appropriately
```

### 3. Story Point Estimation
```javascript
// Example: Story Point Calculator
const storyPointCalculator = {
  fibonacci_scale: [1, 2, 3, 5, 8, 13, 21],
  
  calculateComplexity(story) {
    return {
      technical: this.assessTechnicalComplexity(story),
      business: this.assessBusinessComplexity(story),
      uncertainty: this.assessUncertainty(story)
    };
  },
  
  recommendPoints(complexity) {
    const total = complexity.technical + 
                 complexity.business + 
                 complexity.uncertainty;
    return this.fibonacci_scale.find(points => points >= total);
  }
};
```

## Team PI Objectives

### 1. Creating PI Objectives
```markdown
Objective Structure:
1. Business Value
   - Customer benefit
   - Revenue impact
   - Cost savings

2. Measurable Outcomes
   - Specific metrics
   - Success criteria
   - Validation method

3. Dependencies
   - Cross-team needs
   - System requirements
   - External factors
```

### 2. PI Planning Process
```markdown
Day 1:
- Business Context
- Architecture Vision
- Team Breakouts
- Draft Plans

Day 2:
- Plan Review
- Risk Assessment
- Plan Adjustments
- Confidence Vote
```

## Real-World Example: E-commerce Platform

### Context
```markdown
Project: Online Retail Platform
Teams: 5 Scrum Teams
Duration: 12-week PI
Objective: Launch Mobile App
```

### Implementation
```markdown
Sprint Structure:
- 6 two-week sprints
- Weekly backlog refinement
- Bi-weekly System Demo

Key Metrics:
- Velocity: 45 points/sprint
- Predictability: 85%
- Quality: 98% test coverage
```

### Results
```markdown
PI Outcomes:
1. Mobile App Launch
   - iOS version released
   - Android in beta
   - 4.5/5 user rating

2. Performance
   - 99.9% uptime
   - 2s average response
   - 50% increase in mobile sales
```

## Practice Questions

1. What is the primary purpose of PI Planning in SAFe?
   - [ ] Technical design
   - [ ] Team alignment and planning
   - [ ] Performance review
   - [ ] Budget allocation

2. How often should backlog refinement occur in a typical two-week sprint?
   - [ ] Daily
   - [ ] Weekly
   - [ ] Bi-weekly
   - [ ] Monthly

3. What is the key difference between Kanban and Scrum in SAFe?
   - [ ] Team size
   - [ ] WIP limits
   - [ ] Planning approach
   - [ ] All of the above

[Answer key provided in exam prep module] 