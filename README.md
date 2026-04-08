# Schedula ER Design – Step 1: Requirement Extraction

## System Overview

The system is a healthcare appointment platform that allows users to search for doctors, book appointments, manage multiple patient profiles (family members), make payments, communicate with doctors, and receive notifications and reminders.

---

## Modules Identified

1. User Authentication

   * Mobile-based login and registration

2. Doctor Management

   * Browse doctors, view profiles, experience, and availability

3. Appointment Booking

   * Select date, time slot, and consultation type

4. Time Slot Management

   * Slot-based booking to prevent double booking

5. Patient Management

   * Capture patient details (name, age, gender, complaints)

6. Family Profiles

   * One user can manage multiple patients (self, family members)

7. Payment System

   * Online consultation fee payment

8. Chat System

   * Communication between doctor and patient

9. Feedback System

   * Ratings for doctor, clinic, and experience

10. Notification System

* Appointment reminders, cancellations, and re-engagement messages

11. Support System

* User support tickets (open/resolved)

12. External Booking (IVR Integration)

* Appointment booking via external systems

13. Community / Co-patient System

* Patients grouped for shared interactions

---

## Key Entities Identified

* User
* Doctor
* Clinic
* Availability
* TimeSlot
* Appointment
* Patient
* FamilyMapping
* Payment
* Chat
* Feedback
* Notification
* SupportTicket
* IVRAppointment
* Group / CoPatient

---

## Key Observations & Design Insights

* A single user can manage multiple patient profiles, requiring separation of User and Patient entities
* Appointment acts as the central entity connecting booking, payment, chat, and feedback
* TimeSlot abstraction is required to prevent double booking and manage availability efficiently
* Notifications are event-driven and support reminders, cancellations, and re-engagement flows
* The system supports both direct booking and external (IVR-based) appointment creation
* Doctor availability and actual time slots must be handled separately to support scalability and flexibility
