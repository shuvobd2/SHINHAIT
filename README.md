<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Admin Dashboard</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    body {
      background: #f5f7fb;
      color: #1f2937;
    }

    .sidebar {
      position: fixed;
      left: 0;
      top: 0;
      width: 250px;
      height: 100vh;
      background: #111827;
      color: white;
      padding: 25px 15px;
      transition: 0.3s;
    }

    .logo {
      font-size: 24px;
      font-weight: bold;
      text-align: center;
      margin-bottom: 35px;
    }

    .menu {
      list-style: none;
    }

    .menu li {
      margin-bottom: 8px;
    }

    .menu a {
      display: block;
      color: #d1d5db;
      text-decoration: none;
      padding: 13px 15px;
      border-radius: 8px;
      transition: 0.2s;
    }

    .menu a:hover,
    .menu a.active {
      background: #2563eb;
      color: white;
    }

    .main {
      margin-left: 250px;
      min-height: 100vh;
      transition: 0.3s;
    }

    .navbar {
      height: 70px;
      background: white;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 30px;
      box-shadow: 0 1px 5px rgba(0,0,0,0.08);
    }

    .navbar h2 {
      font-size: 22px;
    }

    .admin {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .avatar {
      width: 40px;
      height: 40px;
      background: #2563eb;
      color: white;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
    }

    .content {
      padding: 30px;
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
      margin-bottom: 30px;
    }

    .card {
      background: white;
      padding: 22px;
      border-radius: 12px;
      box-shadow: 0 3px 12px rgba(0,0,0,0.06);
    }

    .card .label {
      color: #6b7280;
      font-size: 14px;
      margin-bottom: 10px;
    }

    .card .number {
      font-size: 28px;
      font-weight: bold;
    }

    .blue {
      color: #2563eb;
    }

    .green {
      color: #16a34a;
    }

    .orange {
      color: #ea580c;
    }

    .red {
      color: #dc2626;
    }

    .table-box {
      background: white;
      border-radius: 12px;
      padding: 25px;
      box-shadow: 0 3px 12px rgba(0,0,0,0.06);
      overflow-x: auto;
    }

    .table-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
    }

    .table-header h3 {
      font-size: 19px;
    }

    .btn {
      border: none;
      background: #2563eb;
      color: white;
      padding: 10px 16px;
      border-radius: 7px;
      cursor: pointer;
    }

    .btn:hover {
      background: #1d4ed8;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      min-width: 650px;
    }

    th,
    td {
      padding: 14px 12px;
      text-align: left;
      border-bottom: 1px solid #e5e7eb;
    }

    th {
      color: #6b7280;
      font-size: 14px;
    }

    .status {
      padding: 5px 10px;
      border-radius: 20px;
      font-size: 12px;
      background: #dcfce7;
      color: #15803d;
    }

    .status.inactive {
      background: #fee2e2;
      color: #b91c1c;
    }

    .menu-btn {
      display: none;
      background: none;
      border: none;
      font-size: 25px;
      cursor: pointer;
    }

    @media (max-width: 1000px) {
      .cards {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    @media (max-width: 700px) {
      .sidebar {
        left: -250px;
      }

      .sidebar.show {
        left: 0;
      }

      .main {
        margin-left: 0;
      }

      .menu-btn {
        display: block;
      }

      .navbar {
        padding: 0 15px;
      }

      .content {
        padding: 20px 15px;
      }

      .cards {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>

<body>

  <!-- Sidebar -->
  <aside class="sidebar" id="sidebar">
    <div class="logo">AdminPanel</div>

    <ul class="menu">
      <li><a href="#" class="active">📊 Dashboard</a></li>
      <li><a href="#">👥 Users</a></li>
      <li><a href="#">📦 Products</a></li>
      <li><a href="#">🛒 Orders</a></li>
      <li><a href="#">💰 Payments</a></li>
      <li><a href="#">📈 Reports</a></li>
      <li><a href="#">⚙️ Settings</a></li>
      <li><a href="#">🚪 Logout</a></li>
    </ul>
  </aside>

  <!-- Main -->
  <main class="main">

    <!-- Navbar -->
    <nav class="navbar">
      <div style="display:flex; align-items:center; gap:15px;">
        <button class="menu-btn" onclick="toggleSidebar()">☰</button>
        <h2>Dashboard</h2>
      </div>

      <div class="admin">
        <div>
          <strong>Admin</strong>
        </div>
        <div class="avatar">A</div>
      </div>
    </nav>

    <!-- Content -->
    <section class="content">

      <!-- Statistics -->
      <div class="cards">

        <div class="card">
          <div class="label">Total Users</div>
          <div class="number blue">12,450</div>
        </div>

        <div class="card">
          <div class="label">Total Orders</div>
          <div class="number green">8,540</div>
        </div>

        <div class="card">
          <div class="label">Revenue</div>
          <div class="number orange">$24,680</div>
        </div>

        <div class="card">
          <div class="label">Pending</div>
          <div class="number red">126</div>
        </div>

      </div>

      <!-- Users Table -->
      <div class="table-box">

        <div class="table-header">
          <h3>Recent Users</h3>
          <button class="btn" onclick="addUser()">+ Add User</button>
        </div>

        <table>
          <thead>
            <tr>
              <th>#</th>
              <th>Name</th>
              <th>Email</th>
              <th>Role</th>
              <th>Status</th>
              <th>Action</th>
            </tr>
          </thead>

          <tbody id="userTable">

            <tr>
              <td>1</td>
              <td>John Doe</td>
              <td>john@example.com</td>
              <td>Admin</td>
              <td><span class="status">Active</span></td>
              <td><button class="btn" onclick="viewUser('John Doe')">View</button></td>
            </tr>

            <tr>
              <td>2</td>
              <td>Sarah Smith</td>
              <td>sarah@example.com</td>
              <td>Editor</td>
              <td><span class="status">Active</span></td>
              <td><button class="btn" onclick="viewUser('Sarah Smith')">View</button></td>
            </tr>

            <tr>
              <td>3</td>
              <td>Michael Brown</td>
              <td>michael@example.com</td>
              <td>User</td>
              <td><span class="status inactive">Inactive</span></td>
              <td><button class="btn" onclick="viewUser('Michael Brown')">View</button></td>
            </tr>

          </tbody>
        </table>

      </div>

    </section>

  </main>

  <script>
    function toggleSidebar() {
      document.getElementById("sidebar").classList.toggle("show");
    }

    function addUser() {
      const name = prompt("Enter user name:");

      if (!name) return;

      const email = prompt("Enter email:");

      if (!email) return;

      const table = document.getElementById("userTable");
      const rowNumber = table.rows.length + 1;

      const row = table.insertRow();

      row.innerHTML = `
        <td>${rowNumber}</td>
        <td>${name}</td>
        <td>${email}</td>
        <td>User</td>
        <td><span class="status">Active</span></td>
        <td>
          <button class="btn" onclick="viewUser('${name.replace(/'/g, "\\'")}')">
            View
          </button>
        </td>
      `;
    }

    function viewUser(name) {
      alert("User: " + name);
    }
  </script>

</body>
</html>
