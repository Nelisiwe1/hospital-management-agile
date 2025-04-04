# Assessment 8: Hospital Management System (HMS)

## **1. Introduction**
The Hospital Management System (HMS) is designed to streamline hospital operations, ensuring efficient patient management, appointment scheduling, billing, and medical record maintenance. This assessment focuses on the key state transitions and workflows within the HMS, represented through UML diagrams.

## **2. State Transition Diagrams**

### **2.1 Patient State Diagram**

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
### **2.2 Appointment State Diagram**

```mermaid
stateDiagram-v2
    [*] --> Scheduled
    Scheduled --> In_Progress : Patient Arrives
    In_Progress --> Completed : Consultation Done
    Scheduled --> Canceled : Patient Cancels
    In_Progress --> Canceled : Doctor Unavailable
    Completed --> [*]
```
### **2.3 Billing State Diagram**

```mermaid
stateDiagram-v2
    [*] --> Generated
    Generated --> Pending : Awaiting Payment
    Pending --> Paid : Payment Successful
    Pending --> Overdue : Payment Delayed
    Overdue --> Paid : Late Payment Received
    Paid --> [*]
```
## **3. Activity Diagrams**

### **3.1 Patient Admission Workflow**

```mermaid
activityDiagram-v2
    start
    :Patient Arrives;
    :Register at Reception;
    decision Is Emergency?
        Emergency --> [Yes] :Immediate Attention Required;
        Emergency --> [No] :Proceed to Normal Admission;
    :Assign Doctor;
    :Doctor Evaluates Patient;
    decision Requires Admission?
        Requires Admission --> [Yes] :Allocate Bed & Ward;
        Requires Admission --> [No] :Prescribe Medication & Discharge;
    :Patient Under Treatment;
    :Monitor Patient Progress;
    decision Ready for Discharge?
        Ready for Discharge --> [Yes] :Finalize Billing & Discharge;
        Ready for Discharge --> [No] :Continue Treatment;
    stop
```

### **3.2 Billing & Payment Workflow**
```mermaid
activityDiagram-v2
    start
    :Generate Bill;
    :Notify Patient of Due Amount;
    decision Payment Done?
        Payment Done --> [Yes] :Update Payment Status;
        Payment Done --> [No] :Send Payment Reminder;
    decision Overdue Payment?
        Overdue Payment --> [Yes] :Apply Late Fee;
        Overdue Payment --> [No] :Process Completion;
    :Confirm Payment Received;
    :Close Billing Case;
    stop
```
### **3.3 Doctor Consultation Workflow**
```mermaid
activityDiagram-v2
    start
    :Patient Arrives for Consultation;
    :Verify Appointment Details;
    decision Doctor Available?
        Doctor Available --> [Yes] :Proceed to Consultation;
        Doctor Available --> [No] :Reschedule Appointment;
    :Doctor Diagnoses Patient;
    :Prescribe Treatment/Medication;
    :Update Medical Records;
    stop
```

## **4. Conclusion**
This assessment presents key UML diagrams to illustrate the state transitions and workflows in a Hospital Management System. These diagrams help visualize patient management, appointment scheduling, billing, and consultation processes, ensuring a clear understanding of system operations and improving hospital efficiency.



