<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <meta charset="UTF-8">
    <title>Wipro Tracker - Premium Management System</title>

    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- SheetJS Library for Excel Export -->
    <script src="https://cdn.sheetjs.com/xlsx-0.20.2/package/dist/xlsx.full.min.js"></script>

    <!-- Firebase SDKs -->
    <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-database-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-auth-compat.js"></script>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(90deg,rgba(163, 94, 3, 1) 0%, rgba(2, 82, 33, 1) 9%, rgba(120, 184, 24, 1) 100%);
            min-height: 100vh;
            padding: 20px;
        }

        @media print {
            body {
                background: white;
                padding: 0;
                margin: 0;
            }
            
            .profile-box, .btn-group, .month-select, .sync-status, .btn-print, .btn-excel,
            .btn-add, .btn-remove, .btn-undo, .btn-redo, .btn-logout, .btn-add-advance, .btn-add-payment,
            .login-container, .header-box {
                display: none !important;
            }
            
            #appContainer {
                display: block !important;
                margin: 0;
                padding: 10px;
            }
            
            .table-container, .payment-table-container, .advance-table-container {
                box-shadow: none;
                margin: 10px 0;
                page-break-inside: avoid;
            }
            
            table {
                page-break-inside: avoid;
                border: 1px solid #000;
            }
            
            th, td {
                border: 1px solid #000 !important;
                padding: 6px !important;
                font-size: 9pt !important;
            }
            
            th {
                background: #067d28 !important;
                color: white !important;
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
            }
            
            @page {
                size: landscape;
                margin: 0.8cm;
            }
        }

        .btn-print { background: linear-gradient(135deg, #f39c12, #e67e22); color: white; }
        .btn-print:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(243,156,18,0.4); }
        
        .btn-excel { background: linear-gradient(135deg, #1B5E20, #2E7D32); color: white; }
        .btn-excel:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(27,94,32,0.4); }
        
        .btn-add-advance { background: linear-gradient(135deg, #9C27B0, #7B1FA2); color: white; }
        .btn-add-advance:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(156,39,176,0.4); }
        
        .btn-add-payment { background: linear-gradient(135deg, #2196F3, #1976D2); color: white; }
        .btn-add-payment:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(33,150,243,0.4); }

        .header-box {
            background: linear-gradient(90deg,rgba(163, 94, 3, 1) 0%, rgba(2, 82, 33, 1) 9%, rgba(120, 184, 24, 1) 100%);
            padding: 20px;
            border-radius: 20px;
            margin-bottom: 25px;
            text-align: center;
        }

        .header-box h1 {
            font-size: clamp(28px, 5vw, 38px);
            font-weight: 800;
            color: #FFD700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .profile-box {
            position: fixed;
            top: 20px;
            right: 20px;
            background: white;
            padding: 12px 20px;
            border-radius: 25px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            z-index: 1000;
        }

        .profile-circle {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(135deg, #f39c12, #e67e22);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 22px;
            font-weight: bold;
            margin: 0 auto 5px;
        }

        .login-container { display: flex; justify-content: center; align-items: center; min-height: 100vh; }
        .login-card {
            background: white;
            padding: 45px 40px;
            border-radius: 30px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
            width: 100%;
            max-width: 450px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        .login-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #f39c12, #e67e22, #f39c12);
        }
        .login-card h2 {
            font-size: 32px;
            margin-bottom: 30px;
            background: linear-gradient(135deg, #f39c12, #e67e22);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .input-group {
            position: relative;
            margin-bottom: 25px;
        }
        .input-group i {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: #f39c12;
            font-size: 18px;
        }
        .input-group input {
            width: 100%;
            padding: 14px 15px 14px 45px;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            font-size: 15px;
        }
        .input-group input:focus {
            border-color: #f39c12;
            outline: none;
        }
        .password-wrapper { position: relative; }
        .password-wrapper .toggle-eye {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            cursor: pointer;
            color: #999;
            left: auto;
        }
        .login-btn {
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, #f39c12, #e67e22);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
        }
        .login-btn:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(243,156,18,0.4); }

        .table-container, .payment-table-container, .advance-table-container {
            overflow-x: auto;
            margin: 20px 0;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        table {
            width: 100%;
            border-collapse: collapse;
            table-layout: auto;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 12px 8px;
            text-align: center;
            vertical-align: middle;
        }
        th {
            background: linear-gradient(90deg,rgba(163, 94, 3, 1) 0%, rgba(2, 82, 33, 1) 9%, rgba(120, 184, 24, 1) 100%);
            color: white;
            white-space: nowrap;
        }
        
        .main-table th:nth-child(1) { width: 50px; }
        .main-table th:nth-child(2) { min-width: 180px; }
        .main-table th:nth-child(3) { min-width: 140px; }
        .main-table th:nth-child(4) { min-width: 140px; }
        .main-table th:nth-child(5) { min-width: 140px; }
        .main-table th:nth-child(6) { min-width: 180px; }
        .main-table th:nth-child(7) { min-width: 150px; }

        .advance-table th:nth-child(1) { width: 50px; }
        .advance-table th:nth-child(2) { min-width: 180px; }
        .advance-table th:nth-child(3) { min-width: 150px; }
        .advance-table th:nth-child(4) { min-width: 140px; }

        .payment-table th:nth-child(1) { width: 50px; }
        .payment-table th:nth-child(2) { min-width: 150px; }
        .payment-table th:nth-child(3) { min-width: 150px; }
        .payment-table th:nth-child(4) { min-width: 150px; }
        .payment-table th:nth-child(5) { min-width: 140px; }

        input, select {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-family: 'Poppins';
            font-size: 13px;
            box-sizing: border-box;
        }

        select {
            cursor: pointer;
        }

        .location-campus { background-color: #C6EFCE !important; }
        .location-offcampus { background-color: #BDD7EE !important; }
        .offer-selected { background-color: #C6EFCE !important; }
        .offer-rejected { background-color: #FFC7CE !important; }
        .offer-progress { background-color: #FFEB9C !important; }
        .offer-hold { background-color: #D9D2E9 !important; }
        .join-joined { background-color: #A9D08E !important; }
        .join-notjoined { background-color: #F4B084 !important; }
        .join-yettojoin { background-color: #FFE699 !important; }
        .mode-cash { background-color: #C6EFCE !important; }
        .mode-accountpay { background-color: #D9D2E9 !important; }

        select:disabled {
            opacity: 1 !important;
            -webkit-text-fill-color: #000000 !important;
            color: #000000 !important;
        }

        .month-select select {
            background: white !important;
        }

        .btn-group {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
            margin: 20px 0;
        }
        button {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 500;
            transition: 0.3s;
        }
        .btn-add { background: linear-gradient(135deg, #11998e, #38ef7d); color: white; }
        .btn-remove { background: linear-gradient(135deg, #e74c3c, #c0392b); color: white; }
        .btn-undo { background: linear-gradient(135deg, #607D8B, #455A64); color: white; }
        .btn-redo { background: linear-gradient(135deg, #00BCD4, #0097A7); color: white; }
        .btn-logout { background: linear-gradient(135deg, #e74c3c, #c0392b); color: white; padding: 6px 15px; font-size: 12px; }
        button:hover { transform: translateY(-2px); box-shadow: 0 3px 10px rgba(0,0,0,0.2); }

        .month-select { text-align: center; margin: 15px 0; }
        .month-select select {
            width: 250px;
            padding: 12px 20px;
            border-radius: 30px;
            border: 2px solid #f39c12;
            font-weight: 600;
            cursor: pointer;
            background: white;
        }

        .sync-status {
            position: fixed;
            bottom: 15px;
            left: 15px;
            background: linear-gradient(135deg, #11998e, #38ef7d);
            color: white;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 11px;
            z-index: 1000;
        }
        .loading {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(0,0,0,0.9);
            color: white;
            padding: 20px 30px;
            border-radius: 10px;
            z-index: 9999;
        }

        .section-title {
            font-size: 18px;
            font-weight: 600;
            padding: 15px 20px 0 20px;
            color: #333;
        }

        @media (max-width: 768px) {
            body { padding: 10px; }
            .profile-box { top: 10px; right: 10px; padding: 8px 12px; min-width: 80px; }
            .profile-circle { width: 40px; height: 40px; font-size: 18px; }
            button { padding: 6px 12px; font-size: 11px; }
            th, td { padding: 8px 4px; font-size: 11px; }
        }
    </style>
</head>

<body>

<div class="login-container" id="loginContainer">
    <div class="login-card">
        <h2>✨ Wipro Tracker</h2>
        <div class="input-group">
            <i class="fas fa-envelope"></i>
            <input type="email" id="email" placeholder="Email Address" onkeypress="handleEnter(event)">
        </div>
        <div class="input-group password-wrapper">
            <i class="fas fa-lock"></i>
            <input type="password" id="password" placeholder="Password" onkeypress="handleEnter(event)">
            <i class="fas fa-eye toggle-eye" onclick="togglePassword()"></i>
        </div>
        <button class="login-btn" onclick="login()">🚀 Login</button>
        <p style="margin-top: 20px; font-size: 12px; color: #888;">
            <strong>Demo Accounts:</strong><br>
            Admin@wipro.com / Bright@369 (Admin - Full Access)<br>
            user@wipro.com / user123 (User - Read Only)
        </p>
    </div>
</div>

<div id="appContainer" style="display: none;">
    <div class="profile-box">
        <div class="profile-circle" id="profileInitial">A</div>
        <div id="userRole" style="font-size: 12px; font-weight: 500;"></div>
        <button class="btn-logout" onclick="logout()">Logout</button>
    </div>

    <div class="header-box">
        <h1>📊 WIPRO TRACKER 🔥</h1>
    </div>

    <div class="month-select">
        <select id="monthDropdown" onchange="changeMonth()"></select>
    </div>

    <div class="btn-group">
        <button class="btn-add" onclick="addNewRow()"><i class="fas fa-plus"></i> Add Row</button>
        <button class="btn-remove" onclick="removeLastRow()"><i class="fas fa-trash"></i> Remove Row</button>
        <button class="btn-undo" onclick="undoLastAction()"><i class="fas fa-undo"></i> Undo</button>
        <button class="btn-redo" onclick="redoLastAction()"><i class="fas fa-redo"></i> Redo</button>
        <button class="btn-print" onclick="printPage()"><i class="fas fa-print"></i> Print</button>
        <button class="btn-excel" onclick="exportToExcel()"><i class="fas fa-file-excel"></i> Export Excel</button>
    </div>

    <!-- Table 1: Main Candidate Table -->
    <div class="table-container">
        <div class="section-title">👥 Candidate Details</div>
        <table class="main-table" id="mainTable">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Candidate Name</th>
                    <th>Drive Location</th>
                    <th>Date of Drive</th>
                    <th>Offer Status</th>
                    <th>Joining Status</th>
                    <th>Remarks</th>
                    <th>Profile Payment (₹)</th>
                </tr>
            </thead>
            <tbody id="tableBody"></tbody>
            <tfoot>
                <tr>
                    <td colspan="7"><strong>TOTAL</strong></td>
                    <td id="totalProfile">₹0</td>
                </tr>
            </tfoot>
        </table>
    </div>

    <!-- Table 2: Advance Payment Details Table -->
    <div class="advance-table-container">
        <div class="section-title">💰 Advance Payment Details</div>
        <table class="advance-table" id="advanceTable">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Advance Amount (₹)</th>
                    <th>Date of Advance Paid</th>
                    <th>Payment Mode</th>
                </tr>
            </thead>
            <tbody id="advanceTableBody"></tbody>
            <tfoot>
                <tr>
                    <td colspan="1"><strong>TOTAL ADVANCE</strong></td>
                    <td id="totalAdvanceAmount"><strong>₹0</strong></td>
                    <td colspan="2"></td>
                </tr>
            </tfoot>
        </table>
    </div>
    <div class="center" style="text-align: center; margin-bottom: 20px;">
        <button class="btn-add-advance" onclick="addAdvanceRow()"><i class="fas fa-plus"></i> Add Advance Row</button>
    </div>

    <!-- Table 3: Payment Tracking Details Table -->
    <div class="payment-table-container">
        <div class="section-title">💳 Payment Tracking</div>
        <table class="payment-table" id="paymentTable">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Amount Paid (₹)</th>
                    <th>Date of Payment</th>
                    <th>Payment Done By</th>
                    <th>Payment Mode</th>
                </tr>
            </thead>
            <tbody id="paymentTableBody"></tbody>
            <tfoot>
                <tr>
                    <td colspan="1"><strong>TOTAL</strong></td>
                    <td id="totalAmountPaid"><strong>₹0</strong></td>
                    <td colspan="3"></td>
                </tr>
            </tfoot>
        </table>
    </div>
    <div class="center" style="text-align: center; margin-bottom: 20px;">
        <button class="btn-add-payment" onclick="addPaymentRow()"><i class="fas fa-plus"></i> Add Payment Row</button>
    </div>
</div>

<div class="sync-status" id="syncStatus">🔥 Real-time Sync Active</div>

<script>
    const firebaseConfig = {
        apiKey: "AIzaSyA0ze6n4ERhn4Bi6_PT6bA3z3h9NOEc_5M",
        authDomain: "wipro-tracker-bdc7d.firebaseapp.com",
        databaseURL: "https://wipro-tracker-bdc7d-default-rtdb.asia-southeast1.firebasedatabase.app/",
        projectId: "wipro-tracker-bdc7d",
        storageBucket: "wipro-tracker-bdc7d.firebasestorage.app",
        messagingSenderId: "881436977116",
        appId: "1:881436977116:web:34b260f9662e726d605119"
    };

    firebase.initializeApp(firebaseConfig);
    const database = firebase.database();
    const auth = firebase.auth();

    let currentUser = null, currentRole = null;
    let undoHistory = [], redoHistory = [];

    function togglePassword() {
        const pwd = document.getElementById("password");
        const eye = document.querySelector(".toggle-eye");
        if (pwd.type === "password") {
            pwd.type = "text";
            eye.classList.remove("fa-eye");
            eye.classList.add("fa-eye-slash");
        } else {
            pwd.type = "password";
            eye.classList.remove("fa-eye-slash");
            eye.classList.add("fa-eye");
        }
    }

    function handleEnter(e) { if (e.key === 'Enter') login(); }

    function showLoading(show) {
        let loader = document.getElementById("loadingOverlay");
        if (!loader && show) {
            loader = document.createElement("div");
            loader.id = "loadingOverlay";
            loader.className = "loading";
            loader.innerHTML = "⏳ Loading...";
            document.body.appendChild(loader);
        } else if (loader && !show) loader.remove();
    }

    function getEmptyRow() {
        return { 
            name: "", location: "Campus", dateOfDrive: "", offerStatus: "Offer Released", 
            joiningStatus: "Joined", remarks: "", profilePayment: "0"
        };
    }

    function getEmptyAdvanceRow() {
        return { advanceAmount: "0", dateOfAdvancePaid: "", paymentMode: "Cash" };
    }

    function getEmptyPaymentRow() {
        return { amountPaid: "0", dateOfPayment: "", paymentDoneBy: "", paymentMode: "Cash" };
    }

    function getLocationColor(loc) { return loc === 'Campus' ? 'location-campus' : 'location-offcampus'; }
    function getOfferColor(s) {
        if (s === 'Offer Released') return 'offer-selected';
        if (s === 'Rejected') return 'offer-rejected';
        if (s === 'Offer Pending') return 'offer-progress';
        return 'offer-hold';
    }
    function getJoinColor(s) {
        if (s === 'Joined') return 'join-joined';
        if (s === 'Not Joined') return 'join-notjoined';
        return 'join-yettojoin';
    }
    function getPaymentModeColor(mode) {
        return mode === 'Cash' ? 'mode-cash' : 'mode-accountpay';
    }

    function applyColor(select, type, val) {
        if (type === 'location') select.className = getLocationColor(val);
        else if (type === 'offer') select.className = getOfferColor(val);
        else if (type === 'join') select.className = getJoinColor(val);
        else if (type === 'mode') select.className = getPaymentModeColor(val);
    }

    function safeParseNumber(value) {
        const num = parseFloat(value);
        return isNaN(num) ? 0 : num;
    }

    function getMonthYearFromDate(dateStr) {
        if (!dateStr) return null;
        const date = new Date(dateStr);
        if (isNaN(date.getTime())) return null;
        const months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
        return `${months[date.getMonth()]} ${date.getFullYear()}`;
    }

    // Candidate Table Functions
    function renderCandidateTable(rows) {
        const tbody = document.getElementById("tableBody");
        if (!tbody) return;
        tbody.innerHTML = "";
        const isAdmin = currentRole === 'admin';

        rows.forEach((row, idx) => {
            const tr = document.createElement("tr");
            const disabled = !isAdmin ? 'disabled' : '';
            const readonly = !isAdmin ? 'readonly' : '';

            tr.innerHTML = `
                <td>${idx+1}</td>
                <td><input type="text" value="${escapeHtml(row.name)}" ${readonly} onchange="saveAllData();" style="min-width:150px;"></td>
                <td><select id="loc_${idx}" ${disabled} onchange="saveAllData();"><option ${row.location==='Campus'?'selected':''}>Campus</option><option ${row.location==='Off Campus'?'selected':''}>Off Campus</option></select></td>
                <td><input type="date" value="${row.dateOfDrive || ''}" ${readonly} onchange="saveAllData();" style="min-width:130px;"></td>
                <td><select id="off_${idx}" ${disabled} onchange="saveAllData();"><option ${row.offerStatus==='Offer Released'?'selected':''}>Offer Released</option><option ${row.offerStatus==='Rejected'?'selected':''}>Rejected</option><option ${row.offerStatus==='Offer Pending'?'selected':''}>Offer Pending</option><option ${row.offerStatus==='On Hold'?'selected':''}>On Hold</option></select></td>
                <td><select id="join_${idx}" ${disabled} onchange="saveAllData();"><option ${row.joiningStatus==='Joined'?'selected':''}>Joined</option><option ${row.joiningStatus==='Not Joined'?'selected':''}>Not Joined</option><option ${row.joiningStatus==='Yet to Join'?'selected':''}>Yet to Join</option></select></td>
                <td><input type="text" value="${escapeHtml(row.remarks)}" ${readonly} onchange="saveAllData()" style="min-width:150px;"></td>
                <td><input type="number" class="profile-input" value="${row.profilePayment}" ${readonly} oninput="updateCandidateTotals(); saveAllData();" style="min-width:100px;"></td>
            `;
            tbody.appendChild(tr);

            const locSel = document.getElementById(`loc_${idx}`);
            const offSel = document.getElementById(`off_${idx}`);
            const joinSel = document.getElementById(`join_${idx}`);
            
            if(locSel) applyColor(locSel, 'location', row.location);
            if(offSel) applyColor(offSel, 'offer', row.offerStatus);
            if(joinSel) applyColor(joinSel, 'join', row.joiningStatus);
        });
        updateCandidateTotals();
    }

    function updateCandidateTotals() {
        let totalProfile = 0;
        document.querySelectorAll("#tableBody .profile-input").forEach(input => {
            totalProfile += safeParseNumber(input.value);
        });
        document.getElementById("totalProfile").innerHTML = "₹" + totalProfile.toFixed(2);
    }

    function collectCandidateData() {
        const rows = [];
        document.querySelectorAll("#tableBody tr").forEach(tr => {
            const inputs = tr.querySelectorAll("input");
            const selects = tr.querySelectorAll("select");
            rows.push({
                name: inputs[0]?.value || "",
                location: selects[0]?.value || "Campus",
                dateOfDrive: inputs[1]?.value || "",
                offerStatus: selects[1]?.value || "Offer Released",
                joiningStatus: selects[2]?.value || "Joined",
                remarks: inputs[2]?.value || "",
                profilePayment: inputs[3]?.value || "0"
            });
        });
        return rows;
    }

    // Advance Table Functions
    function renderAdvanceTable(rows) {
        const tbody = document.getElementById("advanceTableBody");
        if (!tbody) return;
        tbody.innerHTML = "";
        const isAdmin = currentRole === 'admin';

        rows.forEach((row, idx) => {
            const tr = document.createElement("tr");
            const readonly = !isAdmin ? 'readonly' : '';
            const disabled = !isAdmin ? 'disabled' : '';
            
            tr.innerHTML = `
                <td>${idx+1}</td>
                <td><input type="number" class="advance-amount-input" value="${row.advanceAmount}" ${readonly} oninput="updateAdvanceTotals(); saveAllData();" style="min-width:120px;"></td>
                <td><input type="date" class="advance-date-input" value="${row.dateOfAdvancePaid}" ${readonly} onchange="saveAllData();" style="min-width:130px;"></td>
                <td><select class="advance-mode-select" ${disabled} onchange="saveAllData();">
                    <option ${row.paymentMode === 'Cash' ? 'selected' : ''}>Cash</option>
                    <option ${row.paymentMode === 'Account Pay' ? 'selected' : ''}>Account Pay</option>
                </select></td>
            `;
            tbody.appendChild(tr);
            
            const modeSelect = tr.querySelector('.advance-mode-select');
            if (modeSelect) applyColor(modeSelect, 'mode', row.paymentMode);
        });
        
        updateAdvanceTotals();
    }

    function collectAdvanceData() {
        const rows = [];
        document.querySelectorAll("#advanceTableBody tr").forEach(tr => {
            const inputs = tr.querySelectorAll("input");
            const selects = tr.querySelectorAll("select");
            rows.push({
                advanceAmount: inputs[0]?.value || "0",
                dateOfAdvancePaid: inputs[1]?.value || "",
                paymentMode: selects[0]?.value || "Cash"
            });
        });
        return rows;
    }

    function addAdvanceRow() {
        if (currentRole !== 'admin') { alert("Only admin can add advance rows!"); return; }
        const currentData = collectAdvanceData();
        currentData.push(getEmptyAdvanceRow());
        renderAdvanceTable(currentData);
        saveAllData();
    }

    function updateAdvanceTotals() {
        let totalAdvance = 0;
        document.querySelectorAll("#advanceTableBody .advance-amount-input").forEach(input => {
            totalAdvance += safeParseNumber(input.value);
        });
        document.getElementById("totalAdvanceAmount").innerHTML = `<strong>₹${totalAdvance.toFixed(2)}</strong>`;
    }

    // Payment Table Functions
    function renderPaymentTable(rows) {
        const tbody = document.getElementById("paymentTableBody");
        if (!tbody) return;
        tbody.innerHTML = "";
        const isAdmin = currentRole === 'admin';

        rows.forEach((row, idx) => {
            const tr = document.createElement("tr");
            const readonly = !isAdmin ? 'readonly' : '';
            const disabled = !isAdmin ? 'disabled' : '';
            
            tr.innerHTML = `
                <td>${idx+1}</td>
                <td><input type="number" class="amount-paid-input" value="${row.amountPaid}" ${readonly} oninput="updatePaymentTotals(); saveAllData();" style="min-width:120px;"></td>
                <td><input type="date" class="payment-date-input" value="${row.dateOfPayment}" ${readonly} onchange="saveAllData();" style="min-width:130px;"></td>
                <td><input type="text" class="payment-doneby-input" value="${escapeHtml(row.paymentDoneBy)}" ${readonly} onchange="saveAllData();" style="min-width:150px;"></td>
                <td><select class="payment-mode-select" ${disabled} onchange="saveAllData();">
                    <option ${row.paymentMode === 'Cash' ? 'selected' : ''}>Cash</option>
                    <option ${row.paymentMode === 'Account Pay' ? 'selected' : ''}>Account Pay</option>
                </select></td>
            `;
            tbody.appendChild(tr);
            
            const modeSelect = tr.querySelector('.payment-mode-select');
            if (modeSelect) applyColor(modeSelect, 'mode', row.paymentMode);
        });
        
        updatePaymentTotals();
    }

    function collectPaymentData() {
        const rows = [];
        document.querySelectorAll("#paymentTableBody tr").forEach(tr => {
            const inputs = tr.querySelectorAll("input");
            const selects = tr.querySelectorAll("select");
            rows.push({
                amountPaid: inputs[0]?.value || "0",
                dateOfPayment: inputs[1]?.value || "",
                paymentDoneBy: inputs[2]?.value || "",
                paymentMode: selects[0]?.value || "Cash"
            });
        });
        return rows;
    }

    function addPaymentRow() {
        if (currentRole !== 'admin') { alert("Only admin can add payment rows!"); return; }
        const currentData = collectPaymentData();
        currentData.push(getEmptyPaymentRow());
        renderPaymentTable(currentData);
        saveAllData();
    }

    function updatePaymentTotals() {
        let totalPaid = 0;
        document.querySelectorAll("#paymentTableBody .amount-paid-input").forEach(input => {
            totalPaid += safeParseNumber(input.value);
        });
        document.getElementById("totalAmountPaid").innerHTML = `<strong>₹${totalPaid.toFixed(2)}</strong>`;
    }

    // Save all data to localStorage and Firebase
    function saveAllData() {
        if (currentRole !== 'admin') return;
        
        const candidateData = collectCandidateData();
        const advanceData = collectAdvanceData();
        const paymentData = collectPaymentData();
        
        // Save to localStorage
        localStorage.setItem('candidateData', JSON.stringify(candidateData));
        localStorage.setItem('advanceData', JSON.stringify(advanceData));
        localStorage.setItem('paymentData', JSON.stringify(paymentData));
        
        // Save to Firebase
        database.ref(`candidatesData`).set({ rows: candidateData, lastUpdated: Date.now() });
        database.ref(`advanceData`).set({ rows: advanceData, lastUpdated: Date.now() });
        database.ref(`paymentData`).set({ rows: paymentData, lastUpdated: Date.now() });
        
        updateSyncStatus("✓ Data Saved");
    }

    // Load all data from localStorage or Firebase
    async function loadAllData() {
        let candidateData = localStorage.getItem('candidateData');
        let advanceData = localStorage.getItem('advanceData');
        let paymentData = localStorage.getItem('paymentData');
        
        if (candidateData && advanceData && paymentData) {
            renderCandidateTable(JSON.parse(candidateData));
            renderAdvanceTable(JSON.parse(advanceData));
            renderPaymentTable(JSON.parse(paymentData));
        } else {
            const candidatesSnap = await database.ref(`candidatesData/rows`).once('value');
            renderCandidateTable(candidatesSnap.exists() ? candidatesSnap.val() : Array(5).fill().map(() => getEmptyRow()));
            
            const advanceSnap = await database.ref(`advanceData/rows`).once('value');
            renderAdvanceTable(advanceSnap.exists() ? advanceSnap.val() : []);
            
            const paymentSnap = await database.ref(`paymentData/rows`).once('value');
            renderPaymentTable(paymentSnap.exists() ? paymentSnap.val() : []);
        }
    }

    // Undo/Redo for Candidate Table only
    function saveToUndo() {
        undoHistory.push(JSON.parse(JSON.stringify(collectCandidateData())));
        redoHistory = [];
        if (undoHistory.length > 20) undoHistory.shift();
    }

    function undoLastAction() {
        if (currentRole !== 'admin') { alert("Only admin can undo!"); return; }
        if (undoHistory.length === 0) { alert("Nothing to undo!"); return; }
        redoHistory.push(collectCandidateData());
        renderCandidateTable(undoHistory.pop());
        saveAllData();
    }

    function redoLastAction() {
        if (currentRole !== 'admin') { alert("Only admin can redo!"); return; }
        if (redoHistory.length === 0) { alert("Nothing to redo!"); return; }
        undoHistory.push(collectCandidateData());
        renderCandidateTable(redoHistory.pop());
        saveAllData();
    }

    function addNewRow() {
        if (currentRole !== 'admin') { alert("Only admin can add rows!"); return; }
        saveToUndo();
        const data = collectCandidateData();
        data.push(getEmptyRow());
        renderCandidateTable(data);
        saveAllData();
    }

    function removeLastRow() {
        if (currentRole !== 'admin') { alert("Only admin can remove rows!"); return; }
        const data = collectCandidateData();
        if (data.length === 0) { alert("No rows to remove!"); return; }
        saveToUndo();
        data.pop();
        if (data.length === 0) for (let i=0; i<5; i++) data.push(getEmptyRow());
        renderCandidateTable(data);
        saveAllData();
    }

    function setupRealtime() {
        database.ref(`candidatesData/rows`).on('value', snap => { 
            if (snap.exists()) renderCandidateTable(snap.val()); 
        });
        database.ref(`advanceData/rows`).on('value', snap => { 
            if (snap.exists()) renderAdvanceTable(snap.val()); 
        });
        database.ref(`paymentData/rows`).on('value', snap => { 
            if (snap.exists()) renderPaymentTable(snap.val()); 
        });
    }

    function loadMonths() { 
        const allMonths = ["Mar 2026", "Apr 2026", "May 2026", "Jun 2026", "Jul 2026", "Aug 2026", "Sep 2026", "Oct 2026", "Nov 2026", "Dec 2026", "Jan 2027", "Feb 2027", "Mar 2027"];
        document.getElementById("monthDropdown").innerHTML = allMonths.map(m => `<option ${m===allMonths[0]?'selected':''}>${m}</option>`).join(""); 
    }

    async function changeMonth() {
        const month = document.getElementById("monthDropdown").value;
        const allCandidates = collectCandidateData();
        const filteredCandidates = allCandidates.filter(candidate => {
            const monthYear = getMonthYearFromDate(candidate.dateOfDrive);
            return monthYear === month;
        });
        renderCandidateTable(filteredCandidates.length > 0 ? filteredCandidates : Array(5).fill().map(() => getEmptyRow()));
        updateSyncStatus(`📅 Showing data for ${month}`);
    }

    function applyPermissions() {
        const isAdmin = currentRole === 'admin';
        document.querySelectorAll(".btn-add, .btn-remove, .btn-undo, .btn-redo, .btn-add-advance, .btn-add-payment").forEach(btn => {
            if (btn) btn.style.display = isAdmin ? "inline-block" : "none";
        });
        
        document.querySelectorAll("#appContainer input, #appContainer select").forEach(el => {
            if (!isAdmin) {
                if (el.tagName === 'INPUT') el.setAttribute("readonly", true);
                if (el.tagName === 'SELECT') el.setAttribute("disabled", true);
            } else {
                el.removeAttribute("readonly");
                el.removeAttribute("disabled");
            }
        });
    }

    function exportToExcel() {
        try {
            const candidateRows = collectCandidateData();
            const advanceRows = collectAdvanceData();
            const paymentRows = collectPaymentData();
            
            const wb = XLSX.utils.book_new();
            
            const candidateSheetData = [['#', 'Candidate Name', 'Drive Location', 'Date of Drive', 'Offer Status', 
                               'Joining Status', 'Remarks', 'Profile Payment (₹)']];
            candidateRows.forEach((row, idx) => {
                candidateSheetData.push([idx + 1, row.name, row.location, row.dateOfDrive, row.offerStatus,
                    row.joiningStatus, row.remarks, safeParseNumber(row.profilePayment)]);
            });
            const candidateSheet = XLSX.utils.aoa_to_sheet(candidateSheetData);
            XLSX.utils.book_append_sheet(wb, candidateSheet, 'Candidates');
            
            const advanceSheetData = [['#', 'Advance Amount (₹)', 'Date of Advance Paid', 'Payment Mode']];
            advanceRows.forEach((row, idx) => {
                advanceSheetData.push([idx + 1, safeParseNumber(row.advanceAmount), row.dateOfAdvancePaid, row.paymentMode]);
            });
            const advanceSheet = XLSX.utils.aoa_to_sheet(advanceSheetData);
            XLSX.utils.book_append_sheet(wb, advanceSheet, 'Advances');
            
            const paymentSheetData = [['#', 'Amount Paid (₹)', 'Date of Payment', 'Payment Done By', 'Payment Mode']];
            paymentRows.forEach((row, idx) => {
                paymentSheetData.push([idx + 1, safeParseNumber(row.amountPaid), row.dateOfPayment, row.paymentDoneBy, row.paymentMode]);
            });
            const paymentSheet = XLSX.utils.aoa_to_sheet(paymentSheetData);
            XLSX.utils.book_append_sheet(wb, paymentSheet, 'Payments');
            
            const fileName = `Wipro_Tracker_${new Date().toISOString().slice(0,19).replace(/:/g, '-')}.xlsx`;
            XLSX.writeFile(wb, fileName);
            updateSyncStatus("✓ Excel Exported!", "success");
        } catch (error) {
            console.error("Excel Export Error:", error);
            alert("Error exporting to Excel: " + error.message);
        }
    }

    function printPage() {
        const printWindow = window.open('', '_blank');
        
        const candidateTable = document.querySelector("#mainTable").cloneNode(true);
        const advanceTable = document.querySelector("#advanceTable").cloneNode(true);
        const paymentTable = document.querySelector("#paymentTable").cloneNode(true);
        
        [candidateTable, advanceTable, paymentTable].forEach(table => {
            table.querySelectorAll('select, input').forEach(el => {
                if (el.tagName === 'SELECT') {
                    const selectedText = el.options[el.selectedIndex]?.text || el.value;
                    const span = document.createElement('span');
                    span.textContent = selectedText;
                    span.style.fontWeight = 'bold';
                    el.parentNode.replaceChild(span, el);
                } else {
                    const span = document.createElement('span');
                    span.textContent = el.value || '-';
                    span.style.fontWeight = 'bold';
                    el.parentNode.replaceChild(span, el);
                }
            });
        });
        
        const printHTML = `
            <!DOCTYPE html>
            <html>
            <head>
                <meta charset="UTF-8">
                <title>Wipro Tracker Report</title>
                <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
                <style>
                    * { margin: 0; padding: 0; box-sizing: border-box; }
                    body { font-family: 'Poppins', sans-serif; padding: 20px; background: white; }
                    .print-header { text-align: center; margin-bottom: 30px; padding-bottom: 20px; border-bottom: 3px solid #f39c12; }
                    .print-header h1 { color: #f39c12; font-size: 28px; margin-bottom: 10px; }
                    .print-header p { color: #666; font-size: 12px; margin: 5px 0; }
                    table { width: 100%; border-collapse: collapse; margin-bottom: 30px; page-break-inside: avoid; }
                    th, td { border: 1px solid #000; padding: 8px; text-align: center; font-size: 10pt; }
                    th { background: #067d28; color: white; -webkit-print-color-adjust: exact; print-color-adjust: exact; }
                    @page { size: landscape; margin: 1cm; }
                </style>
            </head>
            <body>
                <div class="print-header">
                    <h1>📊 WIPRO TRACKER REPORT</h1>
                    <p>Generated on: ${new Date().toLocaleString()}</p>
                    <p>User: ${currentUser?.email || 'Unknown'} (${currentRole?.toUpperCase() || 'User'})</p>
                </div>
                <h3>👥 Candidate Details</h3>
                ${candidateTable.outerHTML}
                <h3>💰 Advance Payment Details</h3>
                ${advanceTable.outerHTML}
                <h3>💳 Payment Tracking</h3>
                ${paymentTable.outerHTML}
                <div class="footer" style="text-align:center; margin-top:30px; padding-top:20px; border-top:1px solid #ddd; font-size:10px;">
                    <p>Wipro Tracker System Report</p>
                </div>
            </body>
            </html>
        `;
        
        printWindow.document.write(printHTML);
        printWindow.document.close();
        printWindow.focus();
        setTimeout(() => { printWindow.print(); printWindow.close(); }, 500);
    }

    function updateSyncStatus(msg, err=false) {
        const st = document.getElementById("syncStatus");
        st.innerHTML = msg;
        st.style.background = err ? "#e74c3c" : "linear-gradient(135deg, #11998e, #38ef7d)";
        setTimeout(() => { if(st.innerHTML === msg) { st.innerHTML = "🔥 Real-time Sync Active"; st.style.background = "linear-gradient(135deg, #11998e, #38ef7d)"; } }, 2000);
    }

    async function login() {
        const email = document.getElementById("email").value.trim();
        const pwd = document.getElementById("password").value;
        showLoading(true);
        try {
            const cred = await auth.signInWithEmailAndPassword(email, pwd);
            currentUser = cred.user;
            if (email === "Admin@wipro.com" && pwd === "Bright@369") {
                currentRole = "admin";
            } else if (email === "user@wipro.com" && pwd === "user123") {
                currentRole = "user";
            } else {
                currentRole = email.toLowerCase().includes('admin') ? 'admin' : 'user';
            }
            
            document.getElementById("profileInitial").innerText = email[0].toUpperCase();
            document.getElementById("userRole").innerHTML = `<strong>${currentRole.toUpperCase()}</strong>`;
            document.getElementById("loginContainer").style.display = "none";
            document.getElementById("appContainer").style.display = "block";
            
            loadMonths();
            await loadAllData();
            setupRealtime();
            applyPermissions();
        } catch(e) { 
            alert("Login Failed: " + e.message); 
        }
        finally { showLoading(false); }
    }

    function logout() { auth.signOut().then(() => location.reload()); }
    function escapeHtml(str) { if(!str) return ''; return str.replace(/[&<>]/g, m => ({'&':'&amp;','<':'&lt;','>':'&gt;'}[m])); }

    window.addNewRow = addNewRow;
    window.removeLastRow = removeLastRow;
    window.undoLastAction = undoLastAction;
    window.redoLastAction = redoLastAction;
    window.changeMonth = changeMonth;
    window.saveAllData = saveAllData;
    window.login = login;
    window.logout = logout;
    window.togglePassword = togglePassword;
    window.handleEnter = handleEnter;
    window.printPage = printPage;
    window.exportToExcel = exportToExcel;
    window.addAdvanceRow = addAdvanceRow;
    window.addPaymentRow = addPaymentRow;

    auth.onAuthStateChanged(async user => {
        if(user) {
            currentUser = user;
            const email = user.email;
            if (email === "Admin@wipro.com") {
                currentRole = "admin";
            } else if (email === "user@wipro.com") {
                currentRole = "user";
            } else {
                currentRole = email && email.toLowerCase().includes('admin') ? 'admin' : 'user';
            }
            document.getElementById("profileInitial").innerText = email ? email[0].toUpperCase() : 'A';
            document.getElementById("userRole").innerHTML = `<strong>${currentRole.toUpperCase()}</strong>`;
            document.getElementById("loginContainer").style.display = "none";
            document.getElementById("appContainer").style.display = "block";
            loadMonths();
            loadAllData();
            setupRealtime();
            applyPermissions();
        }
    });
</script>
</body>
</html>
