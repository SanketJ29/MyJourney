# MyJourney - India

**Duration:** June 10, 2025 – July 24, 2025 \
**Author:** Sanket Jaiswal [INDEC] (Sanket.Jaiswal@saint-gobain.com)\
**Target Region:** India\
**Organization:** Saint-Gobain\
**Project Type:** Regional Deployment + Feature Enhancement\
**Audience:** Finance Community of India (Saint-Gobain)

---

## 1. Objective

To localize and enhance the existing Finance Community platform known as MyJourney—originally developed for France and UK—for the Indian finance team at Saint-Gobain.  
The platform serves two main purposes:
- Help employees **explore finance role profiles** across levels and functions.
- Enable users to **shape their personal and professional journey** using structured training paths, learning resources, and role transitions.

---

## 2. Summary of Contributions

- **UI Localization**
  - Adapted all layouts, terminology, and forms to align with Indian finance structure
  - Improved navigation for role discovery and career journey building

- **Master Data Setup**
  - Introduced **new master table for "Job Families"** to support India-specific role hierarchy
    - Job Family → Role → Profile mapping established
    - Legacy systems (France/UK) used only Role–Profile relation
  - Initialized India-specific datasets:
    - Finance job families
    - Roles and associated profiles
    - Skills and training materials
    - Location master and organizational mapping

- **New Functionalities**
  - Designed and integrated **Job Family–Role–Profile navigation flow**
  - Built **hierarchical filters** for Family → Role views
  - Enabled **role editing** during career journey planning
  - Added **gap analysis** between current and future roles
  - Suggested **trainings based on skill gaps**
  - Integrated **Boost platform links** for training resources

- **Backend/API Enhancements**
  - Developed new endpoints to support the updated data structure and navigation flow
  - Refactored existing APIs to align with the new role hierarchy
  - Implemented dynamic filtering logic based on the family–role relationship
  - Added a **user activity tracking table** to log specific actions for analytics and reporting
 
- **Testing & Debugging**
  - Manually validated new workflows, data mappings, and filters
  - Resolved layout and API-related bugs across multiple modules

- **Deployment Support**
  - Participated in QA setup and test data initialization
  - Provided walkthroughs and KT documentation for future teams

---

## 3. Outcome

> The India-specific version of the MyJourney platform is now live, with a revamped master data model, enriched user flows, and regionally tailored content.  
Finance professionals can now plan their development using a more intuitive interface and access targeted learning resources through an integrated journey builder.

---

## 4. Ownership Note

This project was executed **independently over a span of 45 days**, involving full-stack contributions across UI, backend, data modeling, testing, and deployment.  
This document serves both as a **knowledge base** and a **record of contribution** for future handoff or reference.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## Functional & Technical Documentation

This section provides a detailed breakdown of features, logic, database structure, and implementation notes for the India-specific Finance Community platform.

---

### Contents (Module Index)

1. Job Family Structure (New)
2. Role Creation with Family & Profile Mapping (Enhanced)
3. Filtering & Hierarchical Display (New)
4. Gap Analysis & Suggested Trainings (New)
5. Boost Training Links (Manual Addition)
6. Edit Feature in Career Journey Roadmap (Enhanced)
7. User Action Counter & Tracking Logic (New)
8. Backend API Enhancements (New + Modified)
9. Testing, Debugging & Deployment Notes

> **Note:** Role–Profile mapping, authentication, and core roadmap builder features were reused from the existing France/UK implementation and not modified as part of this effort.

---

## 1. Job Family Structure

### Overview

To better organize and categorize finance roles specific to the India region, a new master entity called **Job Family** was introduced. This structure serves as the foundation for grouping related job roles and aligns with the organizational needs of the Finance Community of India.

Previously, the existing platform (France/UK) utilized only a direct Role–Profile mapping. With India's broader categorization needs, Job Families allow better hierarchy, filtering, and scalability in the role exploration process.

---

### Key Highlights

- A new master table for **Job Families** was created in the backend.
- Each **Job Family** can contain multiple associated **Job Roles**.
- UI components were built to support:
  - Displaying families in the role listing section.
  - Selecting a family during new role creation.
- APIs were developed to fetch job families and related roles for both display and admin management.

---

### UI Representation (Back Office)

> A dropdown to select the relevant Job Family was introduced.

![Add Role - Job Family Dropdown](Screenshot%202025-07-24%20120400.png)

---