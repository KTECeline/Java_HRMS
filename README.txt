Teammate 1: User Management – Create, retrieve, update, delete/disable users, and password management.
Teammate 2: Employee Profile Management – Manage employee profiles, including personal information, emergency contacts, working experience, etc.
Teammate 3: Leave, Absence, and Holiday Management – Handle leave applications, approvals, rejections, and leave types.
Teammate 4: Payroll and Attendance Management – Manage payroll processing, generate payslips, and handle time attendance and penalties.



1. Project Structure
Packages:
hrms.usermanagement
hrms.employeeprofile
hrms.leavemanagement
hrms.payroll
hrms.attendance
hrms.utils (for utility classes like file handling, date formatting, etc.)
2. User Management
Classes:
User: Represents a user in the system.
Attributes:
String userID
String username
String password
String role (e.g., System Administrator, HR Officer)
int failedLoginAttempts
boolean isLocked
Constructors:
public User(String userID, String username, String password, String role)
Methods:
public boolean authenticate(String password)
public void resetPassword(String newPassword)
public void lockAccount()
public void unlockAccount()
UserManagement: Manages user-related operations.
Attributes:
List<User> users
Constructors:
public UserManagement()
Methods:
public void createUser(String userID, String username, String password, String role)
public User retrieveUser(String userID)
public void updateUser(String userID, String newUsername, String newPassword, String newRole)
public void deleteUser(String userID)
public void resetUserPassword(String userID, String newPassword)
public void lockUserAccount(String userID)
public void unlockUserAccount(String userID)
3. Employee Profile Management
Classes:
Employee: Extends User and represents an employee.
Attributes:
String personalInfo (e.g., full name, date of birth, etc.)
String emergencyContact
List<String> workExperience
String role
String position
String department
List<String> salaryHistory
Map<String, Integer> leaveEntitlement (e.g., annualLeave, medicalLeave)
double grossSalary
Constructors:
public Employee(String userID, String username, String password, String role, String position, String department)
Methods:
public void updateProfile(String personalInfo, String emergencyContact, List<String> workExperience, String role, String position, String department)
public void updateSalary(double newSalary)
public void addSalaryHistory(String history)
public void updateLeaveEntitlement(String leaveType, int days)
public void viewProfile()
EmployeeManagement: Manages employee profile operations.
Attributes:
List<Employee> employees
Constructors:
public EmployeeManagement()
Methods:
public void createEmployee(String userID, String username, String password, String role, String position, String department)
public Employee retrieveEmployee(String userID)
public void updateEmployee(String userID, String personalInfo, String emergencyContact, List<String> workExperience, String role, String position, String department)
public void deleteEmployee(String userID)
4. Leave, Absence, and Holiday Management
Classes:
LeaveApplication: Represents a leave application.
Attributes:
String applicationID
String employeeID
String leaveType
String startDate
String endDate
String status (Pending, Approved, Rejected)
Constructors:
public LeaveApplication(String applicationID, String employeeID, String leaveType, String startDate, String endDate)
Methods:
public void approveLeave()
public void rejectLeave()
public void cancelLeave()
public String getLeaveStatus()
LeaveManagement: Manages leave applications.
Attributes:
List<LeaveApplication> leaveApplications
Constructors:
public LeaveManagement()
Methods:
public void applyLeave(String applicationID, String employeeID, String leaveType, String startDate, String endDate)
public LeaveApplication retrieveLeaveApplication(String applicationID)
public void approveLeave(String applicationID)
public void rejectLeave(String applicationID)
public void cancelLeave(String applicationID)
5. Payroll Management
Classes:
Payroll: Represents a payroll record for an employee.
Attributes:
String payrollID
String employeeID
double grossSalary
double netSalary
double epfContribution
double socsoContribution
double eisContribution
double pcbContribution (Tax)
Constructors:
public Payroll(String payrollID, String employeeID, double grossSalary)
Methods:
public void calculateDeductions()
public double calculateNetSalary()
public void generatePayslip()
PayrollManagement: Manages payroll operations.
Attributes:
List<Payroll> payrolls
Constructors:
public PayrollManagement()
Methods:
public void createPayroll(String payrollID, String employeeID, double grossSalary)
public Payroll retrievePayroll(String payrollID)
public void updatePayroll(String payrollID, double newGrossSalary)
public void generateMonthlyPayslip(String payrollID)
6. Time Attendance Management
Classes:
AttendanceRecord: Represents an attendance record for an employee.
Attributes:
String recordID
String employeeID
String date
String clockInTime
String clockOutTime
boolean isLate
Constructors:
public AttendanceRecord(String recordID, String employeeID, String date, String clockInTime, String clockOutTime)
Methods:
public void markLate()
public boolean checkLate()
AttendanceManagement: Manages attendance records.
Attributes:
List<AttendanceRecord> attendanceRecords
Constructors:
public AttendanceManagement()
Methods:
public void clockIn(String employeeID, String time)
public void clockOut(String employeeID, String time)
public List<AttendanceRecord> retrieveMonthlyAttendance(String employeeID, String month)
public List<AttendanceRecord> retrieveAnnualAttendance(String employeeID, String year)
7. Utility Classes
FileHandler: Manages file read/write operations.
Attributes:
None (static methods)
Methods:
public static void writeToFile(String fileName, String data)
public static String readFromFile(String fileName)
public static List<String> readLinesFromFile(String fileName)
DateUtils: Handles date formatting and calculations.
Attributes:
None (static methods)
Methods:
public static String formatDate(Date date, String format)
public static Date parseDate(String dateStr, String format)
public static long calculateDaysBetween(Date startDate, Date endDate)
8. Integration and Compilation
Compile the Project:

Each teammate should test their individual modules before integration.
Ensure all modules are properly linked, with methods and data flowing correctly between classes.
Compile the entire project in NetBeans.
Handling Compilation Issues:

Ensure all imported packages and dependencies are correctly set up.
Resolve any conflicts in method signatures or class dependencies.
Testing:

After integration, thoroughly test the system for all functionalities.
Ensure data persistence by saving and loading data to/from files.
Test edge cases, like incorrect data inputs and system boundary conditions.
This detailed breakdown should help you and your teammates effectively divide the work and ensure smooth integration and compilation of your HRMS project.
