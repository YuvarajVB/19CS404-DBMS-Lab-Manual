# ER Diagram Submission - Student Name:YUVARAJ V

## Scenario Chosen:
Hospital 

## ER Diagram:
![Screenshot 2025-05-05 111449](https://github.com/user-attachments/assets/47514eb8-173e-45d7-b672-95fb71814579)


## Entities and Attributes:
- PATIENT: PATIENT_ID (Primary Key),PATIENT_NAME,DOB,GENDER,EMAIL,PH_NO
- DOCTOR: DOCTOR_ID (Primary Key),DOCTOR_NAME,SPECIALIZATION,PH_NO,EMAIL,WORK_SCHEDULE
- APPOINTMENT:APPOINTMENT_ID (Primary Key),DATE_AND_TIME,REASON_FOR_VISIT
- HOSPITAL:No direct attributes shown
- DEPARTMENT:DEPT_ID (Primary Key),DEPT_NAME,DEPT_HEAD


...

## Relationships and Constraints:


*SCHEDULE:

PATIENT schedules APPOINTMENT

Cardinality: One-to-many (one patient can schedule many appointments)

Participation: Total on APPOINTMENT (every appointment must be scheduled by a patient), Partial on PATIENT (a patient may or may not have appointments)

* TAKES:

DOCTOR takes APPOINTMENT

Cardinality: One-to-many (one doctor can take many appointments)

Participation: Total on APPOINTMENT (every appointment must be handled by a doctor), Partial on DOCTOR (not all doctors may have appointments)

* HAVE:

HOSPITAL has DOCTOR

Cardinality: One-to-many (one hospital employs many doctors)

Participation: Total on DOCTOR (every doctor works at a hospital), Partial on HOSPITAL (a hospital may exist even without doctors)

*ASSOCIATION (Unnamed but implied):

HOSPITAL has DEPARTMENT

Cardinality: One-to-many (one hospital can have many departments)

Participation: Total on DEPARTMENT (each department belongs to one hospital), Partial on HOSPITAL (a hospital may have no departments defined)



## Extension (Prerequisite / Billing):
Prerequisite:
Not explicitly modeled, but could be extended by allowing certain appointments (e.g., surgeries) to require pre-appointments (e.g., lab tests). A reflexive relationship on APPOINTMENT (e.g., requires) can model this.

Billing:
Not present in the current diagram. To manage billing, new entities like BILL, PAYMENT, or INVOICE can be added with relationships to PATIENT, APPOINTMENT, and possibly HOSPITAL.
Example attributes for BILL: BILL_ID, AMOUNT, DUE_DATE, STATUS.
## Design Choices:
Entity Separation: Patients, doctors, departments, and appointments are clearly separated, reducing redundancy.

Use of Composite Relationships: SCHEDULE and TAKES appropriately connect appointments with both patients and doctors.

Reflexive or Optional Extensions: Reflexive or optional relationships (like prerequisites or test dependencies) can be added if needed.

Contact Details: Both PATIENT and DOCTOR include contact attributes (EMAIL, PH_NO), which are essential in a real-world system.

Workload Planning: DOCTOR entity includes WORK_SCHEDULE, aiding in shift planning and resource management.

## RESULT
The SCHEDULE relationship allows the system to record which patient has scheduled which appointments, supporting tracking of visits.
The TAKES relationship ensures that each appointment is handled by a doctor, allowing for assignment of responsibilities.
The HAVE relationship captures the organizational structure, linking doctors to the hospitals they work at.
The HOSPITAL–DEPARTMENT connection shows administrative organization, grouping doctors or services under respective departments.
Overall, the ERD sets a solid base for managing hospital data and workflows. With extensions for billing and prerequisite medical processes, it can evolve into a comprehensive hospital management system. 
