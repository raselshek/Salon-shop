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
