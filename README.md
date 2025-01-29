# Salon-shop
Salon shob daily calculation
Ami tomar jonno ekta basic web-based shop management system er prothom dike implementation plan diyechi. Ei system e thakbe:

Core Features:

1. Daily Earnings Tracking

Total daily earnings

Staff percentage share (45% of daily earnings)



2. Staff Earnings Calculation

Total earnings for each staff member based on percentage

Advance payments management (deduct from earnings)



3. Total Earnings Overview

Total earnings of all staff members combined



4. UI Design

Simple, clean, and functional UI with easy-to-read forms and tables.




Technology Stack:

Frontend: HTML, CSS, JavaScript (for dynamic UI)

Backend: Node.js or PHP (for server-side calculations)

Database: MySQL or JSON-based storage (for simplicity)

GitHub Integration: For code versioning


Proposed System Workflow:

1. Daily Earnings Input:

Admin inputs daily sales value in a form.



2. Staff Work Input:

Staff members' names and their earned percentage will be recorded.



3. Advance Calculation:

Admin inputs advance payment amounts, and the system calculates remaining earnings after advance deduction.



4. Output/Display:

Total earnings, staff percentages, and their individual payouts will be displayed in a table format.




UI Design Idea:

Color Scheme: Simple colors like light blue for background, with dark blue for headers and buttons.

Responsive layout: Easy to use on both mobile and desktop.



---

Basic Program (Frontend + Backend Setup)

1. Frontend (HTML/CSS/JavaScript):

An input form for daily earnings, staff details, and percentage.

A table to display total earnings and individual payouts.



2. Backend (Node.js or PHP):

Handle calculations based on inputs and save results.



3. GitHub Workflow:

The code will be pushed to GitHub, where you can view updates, track changes, and run the system.




Example of the flow:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shop Management</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f4f7fa; color: #333; }
        .container { max-width: 1000px; margin: 0 auto; padding: 20px; background: #fff; }
        h1 { color: #0044cc; }
        table { width: 100%; margin-top: 20px; border-collapse: collapse; }
        table th, table td { padding: 8px; border: 1px solid #ddd; text-align: center; }
        input, button { padding: 10px; margin: 10px 0; width: 100%; }
        .result { font-weight: bold; color: #e74c3c; }
    </style>
</head>
<body>

<div class="container">
    <h1>Shop Management System</h1>

    <form id="earningsForm">
        <label for="totalEarnings">Total Daily Earnings:</label>
        <input type="number" id="totalEarnings" required>

        <label for="staffCount">Number of Staff:</label>
        <input type="number" id="staffCount" required>

        <div id="staffInputs"></div>

        <button type="submit">Submit</button>
    </form>

    <div id="result" class="result"></div>

    <h2>Staff Earnings Breakdown:</h2>
    <table id="earningsTable">
        <thead>
            <tr>
                <th>Staff Name</th>
                <th>Percentage (%)</th>
                <th>Earned Amount</th>
            </tr>
        </thead>
        <tbody></tbody>
    </table>
</div>

<script>
    // Dynamically generate staff input fields
    document.getElementById('staffCount').addEventListener('input', function() {
        const count = parseInt(this.value);
        const staffInputs = document.getElementById('staffInputs');
        staffInputs.innerHTML = '';

        for (let i = 1; i <= count; i++) {
            staffInputs.innerHTML += `
                <label for="staff${i}Name">Staff ${i} Name:</label>
                <input type="text" id="staff${i}Name" placeholder="Name of Staff ${i}" required>

                <label for="staff${i}Percentage">Staff ${i} Percentage:</label>
                <input type="number" id="staff${i}Percentage" placeholder="Percentage" required>
            `;
        }
    });

    // Handle form submission and calculations
    document.getElementById('earningsForm').addEventListener('submit', function(e) {
        e.preventDefault();
        
        const totalEarnings = parseFloat(document.getElementById('totalEarnings').value);
        const staffCount = parseInt(document.getElementById('staffCount').value);
        const staffTable = document.getElementById('earningsTable').getElementsByTagName('tbody')[0];

        // Calculate earnings for each staff
        let totalWorkEarnings = 0;
        staffTable.innerHTML = ''; // Clear previous data
        for (let i = 1; i <= staffCount; i++) {
            const staffName = document.getElementById(`staff${i}Name`).value;
            const staffPercentage = parseFloat(document.getElementById(`staff${i}Percentage`).value);
            const staffEarnings = (totalEarnings * staffPercentage) / 100;

            // Add row to table
            const row = staffTable.insertRow();
            row.innerHTML = `<td>${staffName}</td><td>${staffPercentage}%</td><td>${staffEarnings}</td>`;

            totalWorkEarnings += staffEarnings;
        }

        // Display total earnings and staff payout
        const totalPayout = totalEarnings - totalWorkEarnings;
        document.getElementById('result').innerHTML = `Total Earnings: ${totalEarnings}<br>Staff Payouts: ${totalWorkEarnings}<br>Remaining Earnings: ${totalPayout}`;
    });
</script>

</body>
</html>

Steps to Implement:

1. Copy this code to your local machine or GitHub repository.


2. Set up Node.js (if backend logic is needed), or use this HTML code directly for frontend testing.


3. Test it locally using any server or simply by opening the HTML file in the browser.


4. Push it to GitHub to keep track of changes and implement more features as needed.



GitHub Workflow:

1. Create a new repository and add this code.


2. Commit changes and push them to GitHub.


3. View the repository for any changes, and others can also contribute to it.



Ekhon, tumi ki ei code try korte chau? Ar jodi kono further feature chai, ami add korte parbo!

