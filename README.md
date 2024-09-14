# technical-question--5
1. Overview
This document outlines the design and functional requirements for the User Management Screen in the application. The goal of this interface is to allow administrators to manage user accounts, including viewing, adding, editing, and removing users. The page will consist of a list of users, action buttons, and a modal form for user details.

2. Initial State
Upon loading the User Management Screen:

The screen should display a table with a list of existing users.
An "Add User" button should be visible in the top-right corner of the screen.
The list should initially display the following columns:
User ID
Username
Email Address
Role
Status (Active/Inactive)
Actions (Edit/Delete)
If no users are available, display a message:

"No users found. Click 'Add User' to create a new user."
3. UI Components and Behavior
3.1 Table - User List
Columns:
User ID: Display the unique identifier for each user.
Username: Display the username.
Email Address: Display the user’s email.
Role: Display the role (e.g., Admin, User).
Status: Show if the user is Active or Inactive (text with colored label).
Actions: Include "Edit" and "Delete" buttons for each user.
Pagination:
The table should include pagination controls at the bottom (e.g., "Next", "Previous", Page Numbers).
Default page size: 10 users per page.
Allow users to select the number of entries per page (10, 25, 50).
Sorting:
The table columns should be sortable. Clicking on a column header should toggle between ascending and descending order.
3.2 Search Bar
The search bar should be positioned at the top-left of the table.
Users should be able to search by username or email address.
The search results should dynamically update the table.
3.3 Filter Dropdowns
Filter by Role: A dropdown to filter users by role (Admin, User, Guest).
Filter by Status: A dropdown to filter users by their status (Active, Inactive).
The filters should work in combination and update the user list dynamically.
3.4 Add User Button
Positioned at the top-right corner of the screen.
Clicking the "Add User" button will open a modal form for creating a new user.
3.5 Edit and Delete Buttons
Each row in the user table has an "Edit" and a "Delete" button under the "Actions" column.
Edit Button: Opens the user details in the same modal form for editing. The "Save" button updates the existing user.
Delete Button: Opens a confirmation dialog. After confirmation, the user is removed from the list, and a success message appears.
3.6 Modal - Add/Edit User
The modal form will contain the following fields:
Username (Text input)
Email (Text input, email validation required)
Password (Password input, for new users only)
Role (Dropdown)
Status (Dropdown, Active/Inactive)
Form Behavior:
For new users, all fields are editable.
For editing users, the password field should be hidden, and the username and email fields should be pre-populated.
Form Buttons:
Save: Saves the new or updated user.
Cancel: Closes the modal without saving changes.
Form Validation:
Display error messages for invalid fields (e.g., invalid email, empty required fields).
Prevent form submission until all validation criteria are met.
3.7 Confirmation Dialog for Deletion
A modal dialog should appear when a user clicks "Delete" in the actions column.
The dialog should contain the following:
Message: "Are you sure you want to delete this user?"
Buttons:
Confirm: Deletes the user and closes the dialog.
Cancel: Closes the dialog without making changes.
4. Responsive Design
The page should be fully responsive and optimized for both desktop and mobile devices:

Desktop: The table layout should display all columns as described.
Mobile: The table should collapse into a more compact view where only the essential fields (e.g., Username, Role, Actions) are displayed. Other fields should be accessible via expandable rows or icons.
5. Error Handling
In case of failed operations (e.g., user deletion failure due to a server error), display an error notification.
Error messages should appear inline with specific form fields during validation failures.
6. Success Messages
After successfully adding, editing, or deleting a user, display a toast notification (e.g., "User added successfully", "User updated", "User deleted").
