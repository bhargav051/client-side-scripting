# Program Management System

## Overview
This repository contains the code and instructions for creating a Program Management System using Frappe. The system allows managing programs and their associated items. Each program can have multiple items, and the items are managed through a user-friendly interface with custom buttons and dialog boxes.

## Features
- **Parent Doctype: Program**
  - Program Name (Data, required)
  - Program Items (Table, linked to Program Item, read-only)
- **Child Doctype: Program Item**
  - Item Group (Link to Item Group, required)
  - Item (Link to Item, required, filtered by Item Group)
  - Item Name (Data, read-only, fetched from Item)
  - Quantity (Int, required)
  - Finish (Check)
  - Description (Text, required)
- Custom UI Buttons and Dialogs for adding and updating program items.

## Installation

1. **Set up your Frappe environment** if you haven't already. You can follow the [official documentation](https://frappeframework.com/docs/v13/user/en/installation) for setting up Frappe.

2. **Clone this repository** to your Frappe applications directory:
    ```sh
    git clone https://github.com/your-username/program-management-system.git
    ```

3. **Install the app** in your Frappe site:
    ```sh
    bench get-app program_management_system
    bench --site your-site-name install-app program_management_system
    ```

## Setup

1. **Create Parent Doctype: Program**
   - Go to the Frappe desk and navigate to "Doctype" under the "Program Management" module.
   - Create a new Doctype named "Program".
   - Add the following fields:
     - Program Name (Data, required)
     - Program Items (Table, linked to Program Item, read-only)

2. **Create Child Doctype: Program Item**
   - Go to the Frappe desk and navigate to "Doctype" under the "Program Management" module.
   - Create a new Doctype named "Program Item" and set it as a child table.
   - Add the following fields:
     - Item Group (Link to Item Group, required)
     - Item (Link to Item, required, filtered by Item Group)
     - Item Name (Data, read-only, fetched from Item)
     - Quantity (Int, required)
     - Finish (Check)
     - Description (Text, required)

3. **Link Child Doctype to Parent Doctype**
   - Ensure that the "Program Items" field in the Program Doctype is linked to the Program Item Doctype.

4. **Implement Custom UI Buttons and Dialogs**
   - Add two custom buttons to the Program Doctype:
     - "Add New Item"
     - "Update Item"
   - For "Add New Item":
     - Open a dialog box to enter details for a new program item.
     - Include fields: Item Group, Item (filtered by Item Group), Item Name (fetched from Item), Quantity, Finish, Description.
     - On submit, add the new item to the Program Items table.
   - For "Update Item":
     - Open a dialog box to select an item from the Program Items table.
     - Display all existing items in the child table, excluding items where the Finish field is checked.
     - Allow updating fields: Quantity, Finish, Description. Other fields are non-editable.
     - On submit, update the selected item in the Program Items table.

## Usage

1. **Adding a New Program**
   - Navigate to the Program list and click on "New".
   - Enter the program name and save the document.

2. **Managing Program Items**
   - Open an existing Program document.
   - Use the "Add New Item" button to add items to the program.
   - Use the "Update Item" button to update existing items.

## Contribution
Feel free to contribute to this project by creating pull requests, reporting issues, or suggesting improvements.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgements
This project is built using the Frappe framework. Special thanks to the Frappe team for their continuous support and development of this framework.
