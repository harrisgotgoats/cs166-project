ER Diagram Website: https://erdplus.com/
Download the erdplus file and import it to the website to see/edit the diagram

Entities:
	Doctor 
	Patient 
	Maintenance Request 
	Maintenance Staff
	Hospital
	Hospital Department

Attribute Explanation
	"appointment with" relationship's attribute isActive
		denotes whether the appointment has past or not
		designed so you can search for past appointments
	"appointment with" relationship attribute isEmpty
		denotes whether the doctor's timeslot is free or not
		TODO: this also means that patient can be NULL (check for dat)
		
		designed so Patients can search for available time slots
		

	"Hospital Department"'s entity attribute PatientsPerHour
		Assumes each hospital department keeps track of patients per hour
		Wouldn't make sense if it were per doctor
		TODO: Might also be included under the "Hospital" entity for future refence
		designed so doctors search for it

Constraint Justification:
	"part of"
		Hospital Departments must be a part of exactly 1 Hospital
		Hospitals can have any number of hospital departments
	"works in"
		Hospitals can have any number of maintenance staff and doctors
		Doctors can work in any number of Hospitals
		Maintenance Staff can work in any number of Hospitals
	"handles"
		Maintenance Staff can handle any number of Maintenance Requests
		Requests can be handled by any number of Maintenance Staff
	"makes"
		Unique Maintenance Requests can be made by 1 Doctor
		Doctors can make any number of Maintenance Requests
	"has"
		Doctors can have any number of Patients
		Patients can have any number of Doctors
	"on waitlist for"
		Doctors can have any number of Patients on the waitlist
		Patients can be on the waitlist for any number of Doctors
	"appointment with"
		Doctors can have appointments for any number of Patients
		Patients can have appointments for any number of Doctors
