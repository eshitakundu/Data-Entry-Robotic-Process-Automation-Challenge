# UiPath Project: Dynamic Folder Management, Automated Data Entry, and Conditional Screenshot Capture

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Usage Guide](#usage-guide)
- [Requirements](#requirements)
- [License](#license)

---

## Project Overview

This UiPath automation project is designed to manage files dynamically, automate data entry, and capture screenshots as part of an end-to-end process. It includes optimizations for efficiency and adaptability, making it suitable for environments requiring dynamic folder management, data downloads, and visual confirmation.

## Features

- **Dynamic Folder Creation**: Automatically creates `input` and `output` folders if they don’t exist, ensuring seamless file management.
- **File Download**: Downloads an Excel file from a specified website and stores it in the dynamically created `input` folder for easy access.
- **Optimized Data Entry**: Automates data entry using a **Parallel** activity combined with **Set Text**, significantly improving execution speed.
- **Conditional Logic with Pick Branch**: Uses a **Pick Branch** activity to handle scenarios where the website may have closed or reset. This feature ensures the automation can resume by clicking **Reset** if necessary before starting data entry.
- **Screenshot Capture**: Takes a screenshot after form submission and saves it in the `output` folder, allowing for visual verification of the completion.

## Project Structure

```plaintext
Project Folder
├── Main.xaml                   # Central workflow to invoke each sub-workflow in sequence
├── FolderCreation.xaml         # Workflow to dynamically create 'input' and 'output' folders
├── Data Entry.xaml             # Workflow to automate data entry using Parallel and Set Text activities
├── Screenshot.xaml             # Workflow to capture and save a screenshot after submission
└── README.md                   # Project documentation
```

## Setup Instructions

### Prerequisites

- **UiPath Studio**: This project requires UiPath Studio with support for UIAutomation activities.
- **Internet Access**: The project involves interacting with web applications, so a stable internet connection is necessary.

### Installing Dependencies

1. Open the project in **UiPath Studio**.
2. Go to **Manage Packages** > **All Packages**.
3. Ensure that **UiPath.UIAutomation.Activities** and **UiPath.System.Activities** are installed and updated to the latest versions.

## Usage Guide

### 1. Folder Creation

- The **FolderCreation.xaml** workflow ensures the required folders are set up:
  - `input` folder: Used for storing downloaded files (Excel).
  - `output` folder: Used for saving the screenshot after automation.
- These folders are created dynamically within the project’s root directory, making the project adaptable to different systems.

### 2. File Download

- The project includes a step to download an Excel file directly from a specified website and store it in the `input` folder. This file is then used as part of the data entry process.

### 3. Data Entry with Optimizations

- The **Data Entry.xaml** workflow automates data entry into a target application or webpage.
- **Parallel Activity** and **Set Text**: This combination is used for faster data entry, improving efficiency by inputting data concurrently where possible.
- **Pick Branch**: A **Pick Branch** activity is used to detect if the target website has closed or reset. If so, the workflow will click **Reset** before proceeding to the **Start** button, ensuring data entry can continue without manual intervention.

### 4. Screenshot Capture

- The **Screenshot.xaml** workflow captures a screenshot after data entry and form submission, showing the completion state.
- The screenshot is saved in the `output` folder for record-keeping or validation purposes.

### Running the Automation

- **Run Main.xaml**: The **Main.xaml** file orchestrates all workflows in sequence:
  - It begins with the folder creation workflow to set up the `input` and `output` folders.
  - Proceeds to the data entry workflow, where the Excel file is downloaded, and data is entered.
  - Ends with the screenshot capture workflow to save a confirmation screenshot in the `output` folder.

## Requirements

- **Operating System**: Windows (compatible with versions supported by UiPath Studio)
- **UiPath Studio**: Latest version with support for the UIAutomation and System activities packages
- **Web Browser**: Chrome or other browsers compatible with UiPath’s browser automation

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

--- 
