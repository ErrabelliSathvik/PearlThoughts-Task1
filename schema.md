# Schema Design

## 1. User

Represents the account holder (login via mobile)

* id (PK)
* mobile_number (unique)
* created_at

---

## 2. Patient

Represents individuals for whom appointments are booked (family support)

* id (PK)
* user_id (FK → User.id)
* name
* age
* gender

---

## 3. Doctor

Represents doctors available for consultation

* id (PK)
* name
* specialization
* experience_years
* rating
* clinic_id (FK → Clinic.id)

---

## 4. Clinic

Represents hospital/clinic information

* id (PK)
* name
* address

---

## 5. Availability

Represents recurring working schedule of doctors

* id (PK)
* doctor_id (FK → Doctor.id)
* day_of_week
* start_time
* end_time

---

## 6. TimeSlot

Represents actual bookable slots for a specific date

* id (PK)
* doctor_id (FK → Doctor.id)
* date
* start_time
* end_time
* is_booked (boolean)

---

## 7. Appointment

Core entity representing a booking

* id (PK)
* user_id (FK → User.id)
* patient_id (FK → Patient.id)
* doctor_id (FK → Doctor.id)
* slot_id (FK → TimeSlot.id)
* status (booked / cancelled / completed / no-show)
* token_number
* consultation_type (online / offline)
* created_at

---

## 8. Payment

Stores payment details for appointments

* id (PK)
* appointment_id (FK → Appointment.id)
* amount
* status (success / failed / pending)
* payment_method
* paid_at

---

## 9. Chat

Stores messages exchanged between doctor and patient

* id (PK)
* appointment_id (FK → Appointment.id)
* sender_type (doctor / patient / system)
* message
* created_at

---

## 10. Feedback

Stores ratings and feedback after consultation

* id (PK)
* appointment_id (FK → Appointment.id)
* doctor_rating
* clinic_rating
* comments

---

## 11. Notification

Stores reminders and system notifications

* id (PK)
* user_id (FK → User.id)
* appointment_id (FK → Appointment.id)
* type (reminder / cancellation / reengagement)
* message
* status (sent / pending)
* created_at

---

## 12. FamilyMapping

Maps users to multiple patients (family members)

* id (PK)
* user_id (FK → User.id)
* patient_id (FK → Patient.id)
* relation (self / spouse / child / parent)

---

## 13. SupportTicket

Stores user support queries

* id (PK)
* user_id (FK → User.id)
* message
* status (open / resolved)
* created_at

---

## 14. IVRAppointment

Represents appointments booked via external systems (IVR)

* id (PK)
* user_id (FK → User.id)
* doctor_id (FK → Doctor.id)
* external_reference
* status

---

## 15. Group

Represents co-patient/community groups

* id (PK)
* doctor_id (FK → Doctor.id)
* created_at

---

## 16. GroupMembers

Links patients to groups

* id (PK)
* group_id (FK → Group.id)
* patient_id (FK → Patient.id)
