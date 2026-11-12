# CPP Roadmap Site

The goal of this site/project is to track my progress in learning CPP, specifically game development/design, through projects that further my understand of the language and design patterns. The learning curriculum consists of 12 progressively challenging projects that are design to improve an understanding in C++ fundamental, software development skills, and game development and design.

The origianl roadmap and visual design were generated using ChapGPT utilizing it's interactive dashboard capabilities. Due to checkbox states and development notes to guaranteed to be saved due to a lack of database or save filing, it was best to move the roadmap to an external source.

This project will translate the UI into a web page from scratch with HTML, CSS, and JavaScript with the AI generated dashboard as the primary design and functional reference.

Additional features will be introduced to improve progress tracking, project organization, testing documentation, and long-term data management.

The website is intended for my personal use but can still be seen by others for experience.

## 1. Project Scope

The website will contain the following:
1. Curriculum Dashboard
  - The central hub of projects
  - Project completion tracker
  - Stretch goal tracker
  - Table of projects along with individual progress
2. Project Tracker
  - All 12 projects
  - Individual project requirements and completion tracking
  - Development specific notes and reflections
  - Project-specific test cases
  - Github URLs to project
3. Technical Milestones
  - Curriculum-wide C++ skill progression
  - Endependent milestone completion tracking
4. Project Standards
  - Individual project quality standards
  - Completion tracking for each standard
5. Data Management
  - Automatic progress saving
  - Data recovery and backup capabilities
  - Progress reset and export options

Additional features should benefit the roadmap rather than replace or modify its requirements.

## 2. Functional Requirements

### 2.1 Curriculum Progress Tracker

The website will automatically calculate the overall progress based on completed mandatory requirements from all projects.

Requirements:
- Display a percentage, fraction, and progress bar of projects completed
- Displays the number of completed, in progress, and not started projects
- Display a percentage, fraction, and progress of mandatory requirements completed
- Displays the number of completed, in progress, and not started mandatory requirements
- Display a percentage, fraction, and progress of stretch goals completed
- Displays the number of completed, in progress, and not started stretch goals
- An option to reset all progress
- All displays will be updated automatically when status of items changes
- Stretch goals will not affect the mandatory requirements progress

#### Progress Calculations

Total overall mandatory requirements progress will be calculated by the sum of all completed mandatory requirements divided by the total number of mandatory requirements. Mandatory requirements include Functional Requirements, Non-Functional Requirements, Technical Requirements,  Deliverables, and Completion Criteria.

Total stretch goals progress will be calculated by the sum of all completed stretch goals divided by the total number of stretch goals.

Projects will not be completed until all mandatory requirements and its completion criteria have been satisfied.

Project status will follow these rules:
- **Not Started**: No requirements have been marked as **Completed** or **In Progress**
- **In Progress**: Any requirement has been marked as **Completed** or **In Progress**, but the project is not complete.
- **Completed**: All requirements and completion criterira have been marked as **Completed**

Stretch goals will have their own goals the can be completed after the project has been finished. Stretch goals will not block the project from being completed.

### 2.2 Project Requirement Tracking

The website will automatically calculate the progress of the individual project based on the mandatory requirements.

Each project will include the following:
- Project Number and Title
- Difficulty Level
- Status
- Curriculum Phase
- Project Objective
- Technical Concepts
- Functional Requirmeents
- Non-Functional Requirements
- Technical Requirements
- Deliverables
- Completion Criteria
- Stretch Goals
- Development Notes and Reflection

Requirements:
- Every individual mandatory requirement and stretch goal must have a drop down selecting the status
- Display project requirements as a percentage, fraction, and progress bar
- Changing any status will update the overall curriculum dashboard
- Changing any status will update the project dashboard
- Requirements must retain their completion status after the website is reopened
- Development Notes and Reflection must retain their content after the website is reopened


### 2.3 Stretch Goal Tracking

Stretch goals will be tracked independently from mandatory requirements

Requirements:
- Every stretch goal will have their own dropdown to select their status
- Display stretch goals as a fraction, percentage, and progress bar for each project
- Changing any status will update the overall curriculum dashboard
- Changing any status will update the project dashboard
- Stretch goals will not affect mandatory project completion

### 2.4 Resetting Progress

The website must provide a way to reset progress

Requirements
- Include an option to reset progress to the entire curriculum
- Include an option to reset progress to an individual project
- Display a confirmation prompt before resetting
- Reset mandatory requirements, stretch goals, and more.
- Resetting will automatically update all progress identifiers.
- Development notes and test cases should be deleted by a progress only reset unless the user explicitly chooses to reset them.

### 2.5 Expandable and Collapsible Project Details

Each project must have an expandable and collapsible section

Expanded display will display the additional information:
- Project Objective
- Mandatory Requirements Completed
- Stretch goals completed
- Test Cases succeeded
- Quick overview information

Requirement
- Project titles and basic progress information must remain visible when collapsed
- Important project information such as completion project, phase, and project status should remain visible when collapsed
- Collapsed sections should not interfere with progress tracking
- Expanding one project should not reset another project's state
- Provide a consistent visual indication of whether a projec tis expanded or collapsed
- Support expanding and collapsing individual projects

### 2.6 Development Notes and Reflection

Each project must have an independent development notes secitons

Requirements:
- Provide a text area for recording development notes
- Allow notes to be edited at any time
- Save notes automatically
- Preserve notes when requirements are checked or unchecked
- Associate notes with their corresponding project
- Notes will be persistent when pages are reloaded
- Allow multiple paragraphs and multiline text

Notes should be used to document challenges, concepts learned, design decisions and possible improvements

### 2.7 Test Case Management

Each project must have its own test case management section.

Users must be able to create, edit, and delete test cases

Each test case must support:
- Test Case ID
- Title
- Status (Complete or Incomplete)
- Description
- Preconditions
- Steps
- Expected Results
- Actual Results

Requirements:
- Users can add new test cases to individual projects
- Users can edit existing test cases
- Users can delete test cases
- Test cases must remain associated with their respective project
- Users can have the option to cancel or save the changes they made
- Test cases must support multiple steps
- Test cases must support multiple preconditions
- Test cases must support adding Shared Preconditions
- Test cases must have an identifiable status
- Test cases must be displayed in an organized and readable format

#### Shared Preconditions

The website must support resuable preconditions that can be reference by multiple test caess.

Requirements:
- Users can create shared preconditions within a single project
- Users can edit shared preconditions
- Users can attach shared preconditions to inidividual test cases
- Test case can reference multiple shared preconditions
- Users can also create individual preconditions that are not shared
- Shared preconditions should be distinguishable from individual preconditions

The following will need to be considered when the user decides to delete a shared precondition:
- A warning should pop up when a user decides to delete a shared precondition
- Check whether the precondition is currently referenced by any test cases
- If referenced, display a warning explaining which test cases are affected and requirement confirmation
- Remove shared precondition reference from all affected test cases
- Do not delete unrelated test case information

### 2.8 Data Persistence and Recovery

The website must preserve user progress and prevent accidental data loss

Requirements:
- Automatically save changes when progress is updated
- Automatically save development notes
- Save test cases when the user clicks `Save`
- Preserve information after refreshing or reopening the website
- Load previously saved information when the website starts
- Handle missing, invalid, or corrupted saved data
- Preserve incomplete saves from overwriting valid existing data
- Provide appropriate error message when saving fails
- Provide a way to restore progress from a backup

Backup and Recovery:
- Allow the user to export their progress as a JSON file
- Allow users to import a previously exported JSON file
- Validate imported data before replacing existing data
- Warn users before importing data that will overwrite existing progress
- Preserve previous data if an import fails
- Provide a way to create manual backups

### 2.9 Technical Milestone Tracking

The website must include a separate section for curriculum-wide technical milestones.

The milestones represent broader C++ skills developed through multiple projects


Requirements:
- Each milestone must have an independent progress bar
- Each milestone will have subtasks



Requirements:
- Display the project ID number
- Display the Project Name
- Display the Project Difficulty Level
- Display the Project Status
- Display the Project Phase and Phase Name

- Display a percentage of the mandatory requirements completed
- Display a fraction of mandatory requirements completed
- Display a progress bar of mandatory requirements completed

- Display a percentage of the stretch goals completed
- Display a fraction of stretch goals completed
- Display a progress bar of stretch goals completed

- Display a dropdown to collapse project details
- Display the project object with technical concepts

- Display a list and fraction of completion for the following:
  - Functional Requirmeents
  - Non-Functional Requirements
  - Technical Requirements
  - Deliverables
  - Completion Criteria
  - Stretch Goals

- Display development notes or reflection as a text box to write in



1. Updating Progress Tracker

The webpage will update the progress tracker whenever a requirement is complete
- Progress bar will update real time when a task is complete/incomplete
- Percentage will update real time when a task is complete/incomplete

2. Updating Stretch Goals

The webpage will update the stretch goals bar whenever a stretch goal is met

3. Reseting all progress

The webpage can reset all progress if the user desires

4. Expand and collapsable details

The webpage can expand and collapse details if the user desires
- Important details will remain present regardless of collapse

5. Test Cases can be added and deleted per project

Webpage will support the user in creating test cases and shared preconditions to keep track
- Test cases will support separate fields to fill out for status, description, preconditions, steps, expected results, and actual results
- Test cases can be added and removed easily
- Shared preconditions can be added to test case preconditions for simplicity
- Removing shared preconditions will remove the shared precondition from the test cases
  - If the shared precondition is in a test case, the user will be warned before doing so.

6. Data will be saved in the back end in case of errors or corruptions.

7. Technical milestone options can be completed to show performance

8. Complete benchmark project standards for each project
- Source control
- Code organization
- Build system
- Testing
- Documentation
- Error Handling
- Code quality
- Completion

## 3. User Interface Requirements

## 4. Data and Application Architecture Requirements

## 5. Non-Functional Requirements

## 6. Testing Requirements

## 7. Acceptance Criteria

The website will be considered functionally complete when:
- All 12 original projects are represented accurately.
- All original curriculum requirements and descriptions are preserved.
- Mandatory project requirements can be checked and unchecked.
- Project progress updates immediately.
- Overall curriculum progress updates immediately.
- Stretch goals are tracked independently.
- Projects receive the correct completion status.
- Development notes can be saved and retrieved.
- Test cases can be created, modified, and deleted.
- Shared preconditions work correctly.
- Technical milestones can be tracked independently.
- All eight benchmark standards can be tracked for each project.
- Data persists after normal browser restarts.
- Users can export and import their progress.
- Data validation and recovery mechanisms work.
- The website is responsive and usable.
- The application passes its essential functional tests.

## 8. Project Goals

The final website will serve as a long-term personal development tracker throughout the entire C++ Curriculum.

It should provide more than a checklist but a central location for tracking programming requirements, documentation, test cases, evaluating self code quality and measuring progress.
