# Assessment 8: Hospital Management System (HMS)

## **1. Introduction**
The Hospital Management System (HMS) is a software application designed to manage the day-to-day operations of a hospital. The system enables the effective and efficient management of hospital administrative tasks, patient care processes, appointment scheduling, billing, and reporting. This assessment provides UML diagrams, including state transition diagrams and activity diagrams, that demonstrate the dynamic behavior and workflows of the HMS.

---

## **2. State Transition Diagrams**
State transition diagrams show the life cycle of objects within the system. Below are the state transitions for patients, appointments, and billing processes.

### **2.1 Patient State Transition Diagram**
```mermaid
stateDiagram-v2
    [*] --> New
    New --> Admitted : Admission Approved
    Admitted --> Under_Treatment : Treatment Started
    Under_Treatment --> Discharged : Treatment Completed
    Discharged --> [*]
    Admitted --> Discharged : Early Discharge
    Under_Treatment --> Admitted : Requires Further Treatment
```

### **2.2 Appointment State Transition Diagram**
```mermaid
stateDiagram-v2
    [*] --> Scheduled
    Scheduled --> In_Progress : Patient Arrives
    In_Progress --> Completed : Consultation Done
    Scheduled --> Canceled : Patient Cancels
    In_Progress --> Canceled : Doctor Unavailable
    Completed --> [*]
```

### **2.3 Billing State Transition Diagram**
```mermaid
stateDiagram-v2
    [*] --> Generated
    Generated --> Pending : Awaiting Payment
    Pending --> Paid : Payment Successful
    Pending --> Overdue : Payment Delayed
    Overdue --> Paid : Late Payment Received
    Paid --> [*]
```
### **2.4 User Account State Transition Diagram**
```mermaid
stateDiagram-v2
    [*] --> Registered
    Registered --> Active : Email Verified
    Active --> Suspended : Violated Policy
    Suspended --> Active : Appeal Accepted
    Active --> Deactivated : User Request
    Deactivated --> [*]
```
### **2.5 Medical Record State Transition Diagram**
```mermaid
stateDiagram-v2
    [*] --> Created
    Created --> Updated : Add New Info
    Updated --> Archived : Patient Discharged
    Archived --> [*]

```
### **2.6 Prescription State Transition Diagram**
```mermaid
stateDiagram-v2
    [*] --> Issued
    Issued --> Dispensed : Pharmacy Confirms
    Dispensed --> Expired : Validity Ends
    Issued --> Expired : Not Collected
    Expired --> [*]

```
### **2.7 Staff Schedule State Transition Diagram**
```mermaid
stateDiagram-v2
    [*] --> Drafted
    Drafted --> Approved : Supervisor Review
    Approved --> Published : Posted to Staff
    Published --> Modified : Staff Request Changes
    Modified --> Approved
    Approved --> [*]

```


---

## **3. Activity Diagrams**
Activity diagrams represent workflows of stepwise activities and actions. Below are key activity diagrams for the HMS.

### **3.1 Patient Admission Workflow**
```mermaid
flowchart TD
    A[Patient Arrives] --> B[Register at Reception]
    B --> C{Is Emergency?}
    C -- Yes --> D[Immediate Attention Required]
    C -- No --> E[Proceed to Normal Admission]
    D --> F[Assign Doctor]
    E --> F
    F --> G[Doctor Evaluates Patient]
    G --> H{Requires Admission?}
    H -- Yes --> I[Allocate Bed & Ward]
    H -- No --> J[Prescribe Medication & Discharge]
    I --> K[Patient Under Treatment]
    K --> L[Monitor Patient Progress]
    L --> M{Ready for Discharge?}
    M -- Yes --> N[Finalize Billing & Discharge]
    M -- No --> K
    N --> O[End]
    J --> O
```

### **3.2 Billing & Payment Workflow**
```mermaid
flowchart TD
    A[Generate Bill] --> B[Notify Patient of Due Amount]
    B --> C{Payment Done?}
    C -- Yes --> D[Update Payment Status]
    C -- No --> E[Send Payment Reminder]
    E --> F{Overdue Payment?}
    F -- Yes --> G[Apply Late Fee]
    F -- No --> H[Wait for Payment]
    G --> I[Confirm Payment Received]
    H --> I
    D --> I
    I --> J[Close Billing Case]
    J --> K[End]
```

### **3.3 Doctor Consultation Workflow**
```mermaid
flowchart TD
    A[Patient Arrives for Consultation] --> B[Verify Appointment Details]
    B --> C{Doctor Available?}
    C -- Yes --> D[Proceed to Consultation]
    C -- No --> E[Reschedule Appointment]
    D --> F[Doctor Diagnoses Patient]
    F --> G[Prescribe Treatment/Medication]
    G --> H[Update Medical Records]
    H --> I[End]
    E --> I
```
### **3.4 User Registration Workflow**
```mermaid
flowchart TD
    A[Open Registration Page] --> B[Enter Details]
    B --> C[Submit Form]
    C --> D[Send Verification Email]
    D --> E{Email Verified?}
    E -- Yes --> F[Activate Account]
    E -- No --> G[Wait or Resend Email]
    F --> H[Login Enabled]
    H --> I[End]
    G --> I

```
### **3.5 Discharge Process Workflow**
```mermaid
flowchart TD
    A[Doctor Approves Discharge] --> B[Update Records]
    B --> C[Prepare Discharge Summary]
    C --> D[Notify Billing Department]
    D --> E[Generate Final Bill]
    E --> F[Collect Payment]
    F --> G[Patient Leaves Hospital]
    G --> H[End]

```
### **3.6 Generate Medical Report Workflow**
```mermaid
flowchart TD
    A[Doctor Requests Report] --> B[Retrieve Patient History]
    B --> C[Compile Diagnosis Summary]
    C --> D[Add Lab Results]
    D --> E[Format Report]
    E --> F[Review by Senior Doctor]
    F --> G[Approve and Sign]
    G --> H[Send to Patient or Print]
    H --> I[End]

```
### **3.7 Book Appointment Workflow**
```mermaid
flowchart TD
    A[Login to Patient Portal] --> B[Search for Doctor/Speciality]
    B --> C[Select Available Slot]
    C --> D[Enter Symptoms or Reason]
    D --> E[Confirm Appointment]
    E --> F[Send Confirmation Email]
    F --> G[End]


```
### **3.8 Patient Feedback Workflow**
```mermaid
flowchart TD
    A[Submit Feedback Form] --> B[Store in System]
    B --> C[Send Acknowledgement Email]
    C --> D{Is it a Complaint?}
    D -- Yes --> E[Assign to Admin for Review]
    D -- No --> F[Store for Improvement]
    E --> G[Resolve & Respond]
    F --> H[Close Feedback]
    G --> I[Close Feedback]
    I --> J[End]
    H --> J



```

---
## **4. Reflecion**
# Reflection on Hospital Management System UML Models

## Granularity Decisions
In designing the state transition and activity diagrams, I focused on balancing simplicity with enough detail to reflect real-world processes. For example, while the `Patient` state transition could include intermediate stages like “Transferred,” I chose to focus on key lifecycle states to avoid overwhelming complexity.

## Agile Process Alignment
Linking user stories and functional requirements from previous assignments helped ensure the diagrams were aligned with user expectations. Activity diagrams naturally supported these stories by showing step-by-step interactions (e.g., booking an appointment or generating a medical report).

## Comparison of Diagrams
- **State diagrams** excel at visualizing the life cycle of individual entities like `Prescription` or `Billing`, especially in systems with conditional paths.
- **Activity diagrams** were better for illustrating workflows involving multiple roles and steps, such as the discharge process or feedback handling.

## Lessons Learned
Creating these diagrams improved my understanding of dynamic system modeling. It also showed how visual tools can communicate complex workflows clearly, which is valuable for both developers and stakeholders in Agile teams.


## **5. Conclusion**
This assessment presented essential UML diagrams to depict the dynamic behavior of the Hospital Management System. The state transition and activity diagrams help visualize the system's process flows including patient handling, appointment scheduling, billing, and consultation. These models provide a clear understanding of system functionalities and can guide further system development and refinement.

---


