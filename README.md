# C++ Roadmap Site

## 1. Project Overview

A personal website for tracking progress through a 12-project C++ learning curriculum focused on C++ fundamentals, software development, and game development.

The website will recreate the original ChatGPT-generated dashboard using HTML, CSS, and JavaScript, with additional features for project organization, testing, and data management.

## 2. Project Scope

The website will include:

- **Curriculum Dashboard:** Overview of all 12 projects and overall progress.
- **Project Pages:** Individual requirements, stretch goals, notes, test cases, and GitHub links.
- **Technical Milestones:** Curriculum-wide C++ skill progression.
- **Project Standards:** Eight quality standards tracked independently for each project.
- **Data Management:** Automatic saving, JSON import/export, backups, and progress resets.

The original curriculum and its requirements must be preserved.

## 3. Functional Requirements

### 3.1 Progress Tracking

Automatically calculate and display:
- Overall project completion.
- Mandatory requirement completion.
- Stretch goal completion.
- Completed, in-progress, and not-started counts.
- Progress percentages, fractions, and bars.

Project statuses:
- **Not Started:** No requirements have been started.
- **In Progress:** At least one requirement has been started, but the project is incomplete.
- **Completed:** All mandatory requirements and completion criteria are satisfied.

Stretch goals are tracked separately and do not affect project completion.

### 3.2 Project Tracking

Each project must include:
- Project number, title, difficulty, and curriculum phase.
- Objective and technical concepts.
- Functional and non-functional requirements.
- Technical requirements, deliverables, and completion criteria.
- Stretch goals.
- Development notes and reflections.
- GitHub repository link.

Requirements must support individual status updates, with progress automatically reflected on the curriculum dashboard.

### 3.3 Dashboard and Project Pages

**Main Dashboard**
- Display all 12 projects.
- Show project status, phase, difficulty, and progress.
- Include expandable/collapsible project summaries.
- Display mandatory requirements, stretch goals, and test case progress.
- Provide navigation to individual project pages.

**Individual Project Pages**
- Display complete project information and requirements.
- Track mandatory requirements and stretch goals.
- Include project-specific test case management.
- Provide development notes and project standards.

### 3.4 Test Case Management

Each project must have its own test case manager supporting creation, editing, deletion, and saving.

Each test case must include:
- ID and title.
- Status (Complete or Incomplete).
- Description.
- Preconditions.
- Steps.
- Expected results.
- Actual results.

**Shared Preconditions**
- Create and edit reusable preconditions within each project.
- Attach multiple shared preconditions to test cases.
- Support individual preconditions.
- Warn users before deleting shared preconditions that are referenced by test cases.
- Remove affected references after confirmation without modifying unrelated test information.

### 3.5 Development Notes

Each project must have an editable notes section supporting multiple paragraphs. Notes must save automatically and remain associated with the correct project.

### 3.6 Technical Milestones

Track the following curriculum-wide milestones independently:

1. C++ Fundamentals (Projects 01–02)
2. Object-Oriented Programming (03–04)
3. Memory Management (05–06)
4. Algorithms and Data Structures (04–05)
5. Build Systems and Testing (01–08)
6. Modern C++ (06–09)
7. Networking (07–11)
8. Software Architecture (07–12)
9. Performance Engineering (09–12)
10. Production-Quality Development (10–12)

Each milestone must support individual subtasks and independent progress tracking. Completing a project must not automatically complete a milestone.

### 3.7 Project Benchmark Standards

Track these eight standards independently for every project:

1. Source Control
2. Code Organization
3. Build System
4. Testing
5. Documentation
6. Error Handling
7. Code Quality
8. Completion

### 3.8 Data Management

- Automatically save progress and development notes.
- Save test cases when changes are confirmed.
- Restore saved information when the website reopens.
- Handle invalid or corrupted data safely.
- Export and import progress using JSON files.
- Validate imported data before replacing existing information.
- Support manual backups and recovery.
- Provide options to reset all progress or an individual project.
- Require confirmation before destructive actions.

A progress-only reset should preserve notes and test cases unless explicitly selected for deletion.

## 4. User Interface Requirements

- Clean, professional, college-course-style design.
- Responsive desktop, tablet, and mobile layouts.
- Consistent spacing, typography, and styling.
- Clear project statuses and progress indicators.
- Easy navigation between the dashboard and project pages.
- Organized layouts for requirements and test cases.
- Immediate visual feedback when progress or data changes.
- Accessible controls and keyboard navigation.

## 5. Data and Application Architecture

Use HTML5, CSS3, JavaScript, and JSON.

- Separate curriculum information from personal progress data.
- Store project information in structured, reusable data objects.
- Use stable IDs to associate projects, requirements, test cases, and shared preconditions.
- Store technical milestones separately from project progress.
- Keep application logic, data management, and presentation organized into separate responsibilities.
- Use localStorage for persistent browser-based progress.
- Avoid unnecessary code duplication and global variables.

## 6. Testing and Acceptance Criteria

Verify that:

- All 12 original projects and requirements are preserved.
- Progress calculations and project statuses are accurate.
- Stretch goals do not affect mandatory progress.
- Project navigation and expandable sections work correctly.
- Notes, requirements, and test cases persist after reopening.
- Test cases and shared preconditions can be managed correctly.
- Technical milestones and benchmark standards track independently.
- JSON import, export, and recovery work correctly.
- Invalid data does not overwrite valid saved information.
- Reset operations require confirmation.
- The website remains responsive and usable.

## 7. Initial Technical Direction

| Component | Technology |
|---|---|
| Structure | HTML5 |
| Styling | CSS3 |
| Application logic | JavaScript |
| Data format | JSON |
| Browser storage | localStorage |

## 8. Project Goal

Create a long-term C++ development tracker that provides a central location for monitoring learning progress, project requirements, testing, documentation, and software quality across all 12 curriculum projects.