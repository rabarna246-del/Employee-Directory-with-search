<!-- index.html -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Employee Directory</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>Employee Directory</h1>
        
        <!-- Add Employee Form -->
        <div class="form-container">
            <input type="text" id="nameInput" placeholder="Name" required>
            <input type="email" id="emailInput" placeholder="Email" required>
            <select id="positionInput" required>
                <option value="" disabled selected>Position</option>
                <option value="Manager">Manager</option>
                <option value="Team Lead">Team Lead</option>
                <option value="Senior Developer">Senior Developer</option>
                <option value="Developer">Developer</option>
                <option value="Junior Developer">Junior Developer</option>
                <option value="Designer">Designer</option>
                <option value="HR Executive">HR Executive</option>
                <option value="Business Analyst">Business Analyst</option>
                <option value="QA Engineer">QA Engineer</option>
                <option value="DevOps Engineer">DevOps Engineer</option>
                <option value="Product Manager">Product Manager</option>
                <option value="Data Scientist">Data Scientist</option>
                <option value="Intern">Intern</option>
                <option value="Other">Other</option>
            </select>
            <button id="addBtn" onclick="addEmployee()">Add</button>
        </div>

        <!-- All Employees Section -->
        <h2>All Employees</h2>
        <ul id="employeeList">
            <!-- Employees will be dynamically added here -->
        </ul>
    </div>

    <script src="script.js"></script>
</body>
</html>

/* style.css */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Georgia', serif;
    background: linear-gradient(135deg, #0a1628 0%, #1a2f4a 100%);
    color: #2c3e50;
    min-height: 100vh;
    padding: 20px;
}

.container {
    max-width: 900px;
    margin: 0 auto;
    background-color: #f5f5f5;
    padding: 40px;
    border-radius: 8px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
}

h1 {
    font-size: 2.5rem;
    color: #1a3a52;
    margin-bottom: 30px;
    font-weight: bold;
    text-align: left;
}

h2 {
    font-size: 1.5rem;
    color: #2c3e50;
    margin-top: 30px;
    margin-bottom: 20px;
    font-weight: 600;
}

/* Form Styling */
.form-container {
    display: flex;
    gap: 10px;
    margin-bottom: 30px;
    flex-wrap: wrap;
}

.form-container input,
.form-container select {
    flex: 1;
    min-width: 150px;
    padding: 12px 15px;
    border: 2px solid #3498db;
    border-radius: 4px;
    font-size: 14px;
    outline: none;
    transition: border-color 0.3s;
    font-family: 'Georgia', serif;
}

.form-container input:focus,
.form-container select:focus {
    border-color: #2980b9;
    background-color: #eef8ff;
}

.form-container input::placeholder {
    color: #7f8c8d;
}

/* Dropdown specific styling */
.form-container select {
    color: #2c3e50;
    cursor: pointer;
    background-color: white;
}

.form-container select option:first-child {
    color: #7f8c8d;
}

.form-container select option:not(:first-child) {
    color: #2c3e50;
}

#addBtn {
    padding: 12px 30px;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 4px;
    font-size: 14px;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s;
}

#addBtn:hover {
    background-color: #2980b9;
    transform: translateY(-2px);
}

#addBtn:active {
    transform: translateY(0);
}

/* Employee List Styling */
#employeeList {
    list-style: none;
    padding: 0;
}

.employee-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 20px;
    margin-bottom: 12px;
    background-color: white;
    border-left: 4px solid #3498db;
    border-radius: 4px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s, box-shadow 0.2s;
}

.employee-item:hover {
    transform: translateX(5px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.employee-info {
    display: flex;
    align-items: center;
    gap: 15px;
    flex: 1;
}

.employee-info span {
    font-size: 15px;
    color: #2c3e50;
}

.employee-name {
    font-weight: bold;
    color: #1a3a52;
    min-width: 150px;
}

.employee-email {
    color: #3498db;
    min-width: 200px;
}

.employee-position {
    color: #555;
    font-style: italic;
}

.delete-btn {
    padding: 8px 20px;
    background-color: #e74c3c;
    color: white;
    border: none;
    border-radius: 4px;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s;
}

.delete-btn:hover {
    background-color: #c0392b;
    transform: scale(1.05);
}

.delete-btn:active {
    transform: scale(0.98);
}

/* Empty State */
.empty-message {
    text-align: center;
    color: #7f8c8d;
    font-style: italic;
    padding: 30px;
    background-color: white;
    border-radius: 4px;
    border: 2px dashed #bdc3c7;
}

/* Responsive Design */
@media (max-width: 768px) {
    .container {
        padding: 20px;
    }

    h1 {
        font-size: 2rem;
    }

    .form-container {
        flex-direction: column;
    }
    .form-container input,
    .form-container select,
    #addBtn {
        width: 100%;
    }

    .employee-item {
        flex-direction: column;
        align-items: flex-start;
        gap: 10px;
    }

    .employee-info {
        flex-direction: column;
        align-items: flex-start;
        gap: 8px;
    }

    .employee-name,
    .employee-email {
        min-width: auto;
    }

    .delete-btn {
        width: 100%;
    }
}

/* Animation for new items */
@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateY(-20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.employee-item {
    animation: slideIn 0.4s ease-out;
}
<!-- script.js -->

// Initialize employees array from localStorage or empty array
let employees = JSON.parse(localStorage.getItem('employees')) || [];

// Load employees when page loads
window.addEventListener('DOMContentLoaded', () => {
    displayEmployees();
});

// Add employee function
function addEmployee() {
    const nameInput = document.getElementById('nameInput');
    const emailInput = document.getElementById('emailInput');
    const positionInput = document.getElementById('positionInput');

    const name = nameInput.value.trim();
    const email = emailInput.value.trim();
    const position = positionInput.value;

    // Validation
    if (name === '' || email === '' || position === '') {
        alert('Please fill in all fields');
        return;
    }

    // Email validation - accepts single character emails like s@gmail.com
    const emailPattern = /^.+@.+..+$/;
    if (!emailPattern.test(email)) {
        alert('Please enter a valid email address');
        return;
    }

    // Check for duplicate email
    const isDuplicate = employees.some(emp => emp.email.toLowerCase() === email.toLowerCase());
    if (isDuplicate) {
        alert('An employee with this email already exists');
        return;
    }

    // Create employee object
    const employee = {
        id: Date.now(),
        name: name,
        email: email,
        position: position
    };

    // Add to array
    employees.push(employee);

    // Save to localStorage
    saveToLocalStorage();

    // Clear inputs
    nameInput.value = '';
    emailInput.value = '';
    positionInput.value = '';

    // Refresh display
    displayEmployees();

    // Focus back to name input
    nameInput.focus();

    // Success message
    console.log('Employee added successfully!');
}

// Display employees function
function displayEmployees() {
    const employeeList = document.getElementById('employeeList');
    employeeList.innerHTML = '';

    if (employees.length === 0) {
        employeeList.innerHTML = '<li class="empty-message">No employees added yet. Add your first employee above!</li>';
        return;
    }

    employees.forEach(employee => {
        const li = document.createElement('li');
        li.className = 'employee-item';
        
        li.innerHTML = `
            <div class="employee-info">
                <span class="employee-name">${escapeHtml(employee.name)}</span>
                <span class="employee-email">${escapeHtml(employee.email)}</span>
                <span class="employee-position">${escapeHtml(employee.position)}</span>
            </div>
            <button class="delete-btn" onclick="deleteEmployee(${employee.id})">Delete</button>
        `;
        
        employeeList.appendChild(li);
    });
}

// Delete employee function
function deleteEmployee(id) {
    // Confirm deletion
    if (confirm('Are you sure you want to delete this employee?')) {
        employees = employees.filter(emp => emp.id !== id);
        saveToLocalStorage();
        displayEmployees();
    }
}

// Save to localStorage
function saveToLocalStorage() {
    localStorage.setItem('employees', JSON.stringify(employees));
}

// Escape HTML to prevent XSS
function escapeHtml(text) {
    const div = document.createElement('div');
    div.textContent = text;
    return div.innerHTML;
}

// Allow Enter key to add employee
document.addEventListener('keypress', (e) => {
    if (e.key === 'Enter') {
        const activeElement = document.activeElement;
        if (activeElement.id === 'nameInput' || 
            activeElement.id === 'emailInput' || 
            activeElement.id === 'positionInput') {
            addEmployee();
        }
    }
});

// Search functionality (bonus feature)
function searchEmployees(searchTerm) {
    const filtered = employees.filter(emp => 
        emp.name.toLowerCase().includes(searchTerm.toLowerCase()) ||
        emp.email.toLowerCase().includes(searchTerm.toLowerCase()) ||
        emp.position.toLowerCase().includes(searchTerm.toLowerCase())
    );
    return filtered;
}





