CREATE TABLE patient_information (
    patient_id INT PRIMARY KEY,
    patient_name VARCHAR(50),
    birth_ymd DATE,
    patient_phone VARCHAR(30),
    email VARCHAR(100),
    accession DATETIME
);
 
CREATE TABLE doctor_information (
    doctor_id INT PRIMARY KEY,
    doctor_name VARCHAR(50),
    specialized_field VARCHAR(50),
    hospital_name VARCHAR(50),
    doctor_phone VARCHAR(30)  
);

 CREATE TABLE clinic_reservation_info (
    clinic_reservation_id INT PRIMARY KEY,
    a_patient_id INT,
    a_doctor_id INT,
    reservation_date DATE,
    reservation_time DATETIME,
    reservation_status VARCHAR(1),
    FOREIGN KEY (a_patient_id) REFERENCES patient_information(patient_id),
    FOREIGN KEY (a_doctor_id) REFERENCES doctor_information(doctor_id)
 );

 CREATE TABLE clinic_record_info (
    clinic_record_id INT PRIMARY KEY,
    b_patient_id INT,
    b_doctor_id INT,
    reservation_date DATE,
    reservation_time DATETIME,
    reservation_status VARCHAR(1),
    FOREIGN KEY (b_patient_id) REFERENCES patient_information(patient_id),
    FOREIGN KEY (b_doctor_id) REFERENCES doctor_information(doctor_id)
);
