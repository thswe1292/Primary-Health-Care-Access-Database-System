# Primary-Health-Care-Access-Database-System
 Overview
The Primary Health Care Management System is a comprehensive database solution developed using Microsoft Access to manage and streamline various primary health care services. This system facilitates efficient management of patient registration, medical care, maternal and child health, reproductive health, training and workshops, and HR processes. The database is designed with VBA and macros to automate tasks, enhance functionality, and provide a user-friendly interface for health care professionals.

Features
Patient Registration: Simplify the patient intake process with a registration form that captures essential demographic and health information.
Medical Care Management: Track patient visits, diagnoses, treatments, and follow-ups in a centralized system.
Maternal and Child Health: Monitor maternal and child health metrics, including antenal care, delivery, postnatal care, nutrition status and child status.
Reproductive Health: Manage reproductive health services, including family planning, consultations, and education programs.
Training and Workshops: Schedule and manage training sessions and workshops for health care staff and community.
Human Resources: Maintain detailed records of staff members, roles, and training history.
Automation and Customization: Use VBA and macros to automate repetitive tasks and customize the system to meet specific organizational needs.

Example VBA Script

'Save record and checking incomplete data'
Private Sub btnSave_Click()
    If IsNull(Me.txtPatientName) Or IsNull(Me.txtDOB) Then
        MsgBox "Please enter all required fields.", vbExclamation
    Else
        DoCmd.RunCommand acCmdSaveRecord
        MsgBox "Patient record saved successfully.", vbInformation
    End If
End Sub

'Export data from excel by command btn'
Private Sub importancdatabtn_Click()
 Dim filepath As String
    filepath = "C:\Users\ENVY\Desktop\CommcareReports\ANCReport.xlsx"
    DoCmd.TransferSpreadsheet acImport, , "ANCTbl", filepath, True
    MsgBox "Done"
  End Sub
