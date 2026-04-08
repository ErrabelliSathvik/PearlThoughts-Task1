# PearlThoughts-Task1
# Schedula ER Design – Step 1: Requirement Extraction

## Modules Identified

1. User Authentication
2. Doctor Management
3. Appointment Booking
4. Time Slot Management
5. Patient Management
6. Payment System
7. Chat System
8. Feedback System
9. Notification System
10. Family Profiles
11. Support System

## Key Entities Identified

* User
* Doctor
* Availability
* TimeSlot
* Appointment
* Patient
* Payment
* Chat
* Feedback
* Notification
* FamilyMapping
* SupportTicket

## Notes / Observations

* One user can manage multiple patients (family members)
* Appointment is the central entity connecting multiple modules
* Time slots are required to prevent double booking
* Notifications are event-driven (reminders, cancellations, re-engagement)
