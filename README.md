<!DOCTYPE html>
<html>
<head>
  <title>Employee Management System</title>
  <style>
    body {
      font-family: monospaced, sans-serif;
      background-color:#FFA07A;
    }

    .container {
      width: 800px;
      margin: 0 auto;
      padding: 20px;
      border: 1px solid #ccc;
    }

    .form-group {
      margin-bottom: 20px;
    }

    .form-group label {
      display: block;
      font-weight: bold;
    }

    .button-group {
      margin-top: 20px;
    }

    .result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
  <script>
    function generatePaySlip() {
      var name = document.getElementById("name").value;
      var branchTeam = document.getElementById("branch-team").value;
      var department = document.getElementById("department").value;
      var fees = parseInt(document.getElementById("fees").value);
      var chennai = parseFloat(document.getElementById("chennai").value);
      var aurangabad = parseFloat(document.getElementById("aurangabad").value);

      document.getElementById("pay-slip-name").textContent = name;
      document.getElementById("pay-slip-branch-team").textContent = branchTeam;
      document.getElementById("pay-slip-department").textContent = department;
      document.getElementById("pay-slip-fees").textContent = fees;
      document.getElementById("pay-slip-chennai").textContent = chennai;
      document.getElementById("pay-slip-aurangabad").textContent = aurangabad;
    }

    function generateCashFlowReport() {
      var fees = parseInt(document.getElementById("fees").value);
      var numEmployees = parseInt(document.getElementById("num-employees").value);
      var chennaiCashFlow = fees * numEmployees;
      var aurangabadCashFlow = chennaiCashFlow;

      document.getElementById("cash-flow-chennai").textContent = chennaiCashFlow;
      document.getElementById("cash-flow-aurangabad").textContent = aurangabadCashFlow;
    }

    function generateBalanceSheetReport() {
      var totalFees = parseInt(document.getElementById("fees").value) * parseInt(document.getElementById("num-employees").value);
      var chennaiSalary = parseFloat(document.getElementById("chennai").value);

      document.getElementById("balance-sheet-fees").textContent = totalFees;
      document.getElementById("balance-sheet-chennai").textContent = chennaiSalary;
    }

    function distributeProfit() {
      var name = document.getElementById("name").value;
      var branchTeam = document.getElementById("branch-team").value;
      var department = document.getElementById("department").value;
      var fees = parseInt(document.getElementById("fees").value);
      var aurangabad = parseFloat(document.getElementById("aurangabad").value);

      document.getElementById("profit-name").textContent = name;
      document.getElementById("profit-branch-team").textContent = branchTeam;
      document.getElementById("profit-department").textContent = department;
      document.getElementById("profit-fees").textContent = fees;
      document.getElementById("profit-aurangabad").textContent = aurangabad;
    }
  </script>
</head>
<body>
  <div class="container">
    <h1>Employee  Management System</h1>

    <form id="management-form">
      <div class="form-group">
        <label for="name">Name:</label>
        <input type="text" id="name" required>
      </div>
      <div class="form-group">
        <label for="branch-team">Branch Team:</label>
        <input type="text" id="branch-team" required>
      </div>
      <div class="form-group">
        <label for="department">Department:</label>
        <input type="text" id="department" required>
      </div>
      <div class="form-group">
        <label for="fees">Fees:</label>
        <input type="number" id="fees" required>
      </div>
      <div class="form-group">
        <label for="chennai">Chennai Salary:</label>
        <input type="number" id="chennai" required>
      </div>
      <div class="form-group">
        <label for="aurangabad">Aurangabad Salary:</label>
        <input type="number" id="aurangabad" required>
      </div>
      <div class="form-group">
        <label for="num-employees">Number of Employees:</label>
        <input type="number" id="num-employees" required>
      </div>
      
      <div class="button-group">
        <button type="button" onclick="generatePaySlip()">Pay Slip Monthly Generated</button>
        <button type="button" onclick="generateCashFlowReport()">Cash Flow Report</button>
        <button type="button" onclick="generateBalanceSheetReport()">Balance Sheet Report</button>
        <button type="button" onclick="distributeProfit()">Stakeholder Distribute (Profit)</button>
      </div>
    </form>
    
    <div class="result">
      <h3>Results:</h3>
      <p><strong>Pay Slip Monthly Generated:</strong></p>
      <p>Name: <span id="pay-slip-name"></span></p>
      <p>Branch Team: <span id="pay-slip-branch-team"></span></p>
      <p>Department: <span id="pay-slip-department"></span></p>
      <p>Fees: <span id="pay-slip-fees"></span></p>
      <p>Chennai: <span id="pay-slip-chennai"></span></p>
      <p>Aurangabad: <span id="pay-slip-aurangabad"></span></p>
      
      <p><strong>Cash Flow Report:</strong></p>
      <p>Chennai Cash Flow: <span id="cash-flow-chennai"></span></p>
      <p>Aurangabad Cash Flow: <span id="cash-flow-aurangabad"></span></p>
      
      <p><strong>Balance Sheet Report:</strong></p>
      <p>Total Fees: <span id="balance-sheet-fees"></span></p>
      <p>Chennai Salary: <span id="balance-sheet-chennai"></span></p>
      
      <p><strong>Stakeholder Distribute (Profit):</strong></p>
      <p>Name: <span id="profit-name"></span></p>
      <p>Branch Team: <span id="profit-branch-team"></span></p>
      <p>Department: <span id="profit-department"></span></p>
      <p>Fees: <span id="profit-fees"></span></p>
      <p>Aurangabad: <span id="profit-aurangabad"></span></p>
    </div>
  </div>
</body>
</html>
