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

---

## **4. Conclusion**
This assessment presented essential UML diagrams to depict the dynamic behavior of the Hospital Management System. The state transition and activity diagrams help visualize the system's process flows including patient handling, appointment scheduling, billing, and consultation. These models provide a clear understanding of system functionalities and can guide further system development and refinement.

---

**End of Assessment 8**
