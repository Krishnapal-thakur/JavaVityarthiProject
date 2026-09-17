# Smart University Library & Resource Management System (ULRMS)

An enterprise-grade Java console application designed to automate university library operations.

## Overview

The Smart University Library & Resource Management System (ULRMS) streamlines the administration of academic libraries. It provides a structured, role-based platform for managing books, users (Students and Faculty), circulation transactions, and the automated calculation of fines using a layered service architecture and background multithreading.

## Features

*   **Role-Based Access Control:** Differentiates between Student and Faculty users with strictly enforced borrowing limits (3 books for Students, 7 for Faculty).
*   **Dynamic Inventory Management:** Real-time tracking of book availability with support for ISBN and Title indexing/search functionality.
*   **Book Circulation Workflow:** Automated processes for issuing books (Checkouts) and managing returns, maintaining precise transaction logs.
*   **Automated Fine Engine:** A multithreaded background daemon auditing system periodically updates fine amounts on overdue transactions.
*   **Robust Exception Handling:** Utilizes a domain-specific custom exception hierarchy (e.g., `BookNotAvailableException`, `BorrowLimitExceededException`) to ensure system stability and clean terminal feedback.

## Technologies/Tools Used

*   **Language:** Java (JDK 17+)
*   **Paradigms:** Object-Oriented Programming (OOP)
*   **Key APIs:** Java Collections Framework (HashMap, List), Concurrency API (background auditing thread), LocalDateTime API.
*   **Build/Run:** Manual compile & run via PowerShell or Bash.

## Steps to Install & Run

### Prerequisites

*   **Java Development Kit (JDK):** Ensure JDK 17 or higher is installed.
*   **System PATH:** Verify the `javac` and `java` commands are accessible in your system’s PATH.

### Build and Run Command (One-line)

Navigate to the project root directory (the folder containing the `src` folder) and execute the single command appropriate for your operating system:

**Windows (PowerShell):**

```powershell
if (!(Test-Path bin)) { New-Item -ItemType Directory bin }; javac -d bin (Get-ChildItem -Path src -Recurse -Filter *.java).FullName; java -cp bin com.library.main.Main
