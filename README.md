Class: AccessControl

Manages access control levels for different roles in a system using an ACL (Access Control List). It detects and resolves permission conflicts, particularly for the “Admin” role.

Attributes:

	1.	acl: A map storing roles as keys and their corresponding permissions as values.
	2.	adminConflictFixed: A flag indicating whether an admin permission conflict has been resolved.

Methods:

	1.	AccessControl():
Constructor that initializes the ACL by calling initializeACL().
	2.	initializeACL():
Populates the ACL with predefined roles and their permissions.
	3.	getAccessLevel(String role):
Retrieves the list of permissions for a given role. If no permissions are found, it returns an appropriate message.
	4.	detectAdminConflict():
Checks if the “Admin” role has a conflict in its permissions (e.g., “Limited Access”) and suggests a fix.
	5.	fixAdminConflict():
Resolves the detected admin conflict by changing “Limited Access” to “Full System Access.”
	6.	isAdminConflictFixed():
Returns true if the admin conflict has already been resolved; otherwise, false.

Class: AcceeControlGUI

A graphical user interface (GUI) for the Bank Access Control System. It allows users to select a role and view the associated permissions, detects conflicts in the Admin role, and provides automatic conflict resolution.

Attributes:

	1.	accessControl: An instance of the AccessControl class to manage role permissions and conflicts.
	2.	ConflictFixed: A flag to track whether the Admin conflict has been resolved.

Methods:

	1.	AcceeControlGUI():
Constructor that initializes the GUI and creates an AccessControl instance.
	2.	initComponents():
Initializes and lays out all GUI components, including panels, labels, buttons, and combo boxes.
	3.	CheackPermissions(ActionEvent evt):
Handles the “Check Permissions” button click. Opens the PermissionsWindow for the selected role and checks for conflicts in the Admin role, resolving them if necessary.
	4.	openPermissionsWindow():
Opens a window to display the selected role’s permissions. Checks for conflicts in the Admin role and displays a warning if needed.
	5.	main(String[] args):
The main method to launch the application.
	6.	jComboBox1ActionPerformed(ActionEvent evt):
Handles actions when a role is selected from the dropdown menu.
	7.	jTextField1ActionPerformed(ActionEvent evt):
Handles actions related to the text field (currently unused).

GUI Components:
1.	jPanel1:
Main panel with a background color and all GUI components.
	2.	jPanel2:
Header panel with the application title.
	3.	jLabel1:
Displays the bank logo.
	4.	jLabel2:
Displays the title “Bank Access System” in the header.
	5.	jTextField1:
Non-editable text field prompting the user to select an access level.
	6.	jComboBox1:
Dropdown menu to select a role (e.g., Client, Employee, Admin).
	7.	jButton1:
Button labeled “Check Permission” to trigger permission checks and conflict detection.

Class: PermissionsWindow

A graphical user interface (GUI) to display the permissions associated with a selected role. It detects and handles any conflicts for the “Admin” role, allowing the user to resolve them interactively.

Attributes:

	1.	role: A string representing the role for which permissions are being displayed (e.g., “Admin”).
	2.	accessControl: An instance of the AccessControl class that manages role-based permissions and conflict detection.
	3.	conflictFixed: A boolean flag to track whether an Admin conflict has been fixed.
	4.	roleComboBox: Unused (can be removed or clarified in code).

Methods:

	1.	PermissionsWindow(String role):
Constructor that initializes the window with the selected role and sets up the permissions for that role.
	2.	initComponents():
Initializes the GUI components, including labels, buttons, text areas, and panels.
	3.	setPermissions(String role):
Sets the permissions for the specified role and checks for conflicts if the role is “Admin”. If a conflict is detected, it prompts the user to resolve it.
	4.	jButton1ActionPerformed(ActionEvent evt):
Handles the “Return” button click, closing the current window and returning to the AcceeControlGUI.
	5.	textArea1ComponentShown(ComponentEvent evt):
Handles events when the text area is shown (currently unused).
	6.	main(String[] args):
The main method to launch the PermissionsWindow with the specified role (in this case, “Admin”).

GUI Components:

	1.	jPanel1:
Main panel containing all other components.
	2.	jPanel2:
Header panel with a background color.
	3.	jLabel1:
Displays an icon representing the user or role.
	4.	jLabel2:
Label prompting “Role :”.
	5.	jLabel4:
Label that displays the selected role name.
	6.	textArea1:
Text area where the permissions for the selected role are displayed. It is non-editable.
	7.	jButton1:
Button labeled “Return” to navigate back to the main AcceeControlGUI.

This class is designed to manage and display permissions for different roles, with specific handling for conflicts related to the Admin role. 


