<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aplikasi CRUD PBO - LocalStorage</title>
    <style>
        * { box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; margin: 0; padding: 0; }
        body { background-color: #f4f6f9; color: #333; }
        
        /* Navigation Bar */
        nav { background: #2c3e50; color: white; padding: 1rem; display: flex; justify-content: space-between; align-items: center; }
        nav .nav-links button { background: none; border: none; color: white; padding: 8px 16px; cursor: pointer; font-size: 14px; }
        nav .nav-links button:hover { background: #34495e; border-radius: 4px; }

        /* Container Pages */
        .container { max-width: 900px; margin: 30px auto; padding: 20px; background: white; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); }
        .page { display: none; }
        .active { display: block; }

        /* Forms & Inputs */
        .form-group { margin-bottom: 15px; }
        .form-group label { display: block; margin-bottom: 5px; font-weight: bold; }
        .form-group input, .form-group select { width: 100%; padding: 10px; border: 1px solid #ccc; border-radius: 4px; }
        
        /* Buttons */
        .btn { padding: 8px 16px; border: none; border-radius: 4px; cursor: pointer; font-weight: bold; }
        .btn-primary { background: #3498db; color: white; }
        .btn-success { background: #2ecc71; color: white; }
        .btn-danger { background: #e74c3c; color: white; }
        .btn-warning { background: #f1c40f; color: black; }
        .btn:hover { opacity: 0.9; }

        /* Table */
        table { width: 100%; border-collapse: collapse; margin-top: 15px; }
        table, th, td { border: 1px solid #ddd; }
        th, td { padding: 12px; text-align: left; }
        th { background-color: #f8f9fa; }

        /* Badges */
        .badge { padding: 4px 8px; border-radius: 4px; color: white; font-size: 12px; font-weight: bold; }
        .badge-admin { background-color: #e74c3c; }
        .badge-standard { background-color: #2ecc71; }

        /* Profile Card */
        .profile-card { border: 1px solid #ddd; padding: 20px; border-radius: 8px; background: #fafafa; }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav id="navbar" style="display: none;">
        <h3>Sistem Kelola User (PBO)</h3>
        <div class="nav-links">
            <button onclick="showPage('page-users')">Daftar User</button>
            <button onclick="showPage('page-profile')">Profil Saya</button>
            <button onclick="logout()" class="btn-danger">Logout</button>
        </div>
    </nav>

    <div class="container">
        <!-- Halaman 1: Login -->
        <div id="page-login" class="page active">
            <h2>Login Sistem</h2>
            <hr><br>
            <form id="loginForm" onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label>Username</label>
                    <input type="text" id="loginUsername" required placeholder="Masukkan username">
                </div>
                <div class="form-group">
                    <label>Password</label>
                    <input type="password" id="loginPassword" required placeholder="Masukkan password">
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Login</button>
            </form>
            <p style="margin-top: 15px; font-size: 13px; color: #666;">
                *Default Login Admin: <b>admin</b> / <b>admin123</b><br>
                *Default Login User: <b>user</b> / <b>user123</b>
            </p>
        </div>

        <!-- Halaman 2: Tabel Daftar User (CRUD) -->
        <div id="page-users" class="page">
            <h2>Manajemen Data User</h2>
            <hr><br>

            <!-- Form Tambah / Edit -->
            <form id="userForm" onsubmit="handleSaveUser(event)">
                <input type="hidden" id="userId">
                <div style="display: flex; gap: 10px;">
                    <div class="form-group" style="flex: 1;">
                        <label>Username</label>
                        <input type="text" id="userName" required>
                    </div>
                    <div class="form-group" style="flex: 1;">
                        <label>Email</label>
                        <input type="email" id="userEmail" required>
                    </div>
                    <div class="form-group" style="flex: 1;">
                        <label>Role (Polimorfisme)</label>
                        <select id="userRole">
                            <option value="Admin">Admin</option>
                            <option value="Standard">Standard User</option>
                        </select>
                    </div>
                </div>
                <button type="submit" id="btnSubmit" class="btn btn-success">Tambah User</button>
                <button type="button" onclick="resetForm()" class="btn btn-warning">Batal</button>
            </form>

            <br><hr><br>

            <!-- Tabel User -->
            <table>
                <thead>
                    <tr>
                        <th>ID</th>
                        <th>Username</th>
                        <th>Email</th>
                        <th>Role & Badge</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody id="userTableBody">
                    <!-- Data akan dirender dari JS -->
                </tbody>
            </table>
        </div>

        <!-- Halaman 3: Profile -->
        <div id="page-profile" class="page">
            <h2>Profil Pengguna</h2>
            <hr><br>
            <div class="profile-card">
                <h3 id="profName">-</h3>
                <p><strong>Email:</strong> <span id="profEmail">-</span></p>
                <p><strong>Role:</strong> <span id="profRole">-</span></p>
                <p style="margin-top: 10px;"><strong>Hak Akses Sistem (Polimorfisme):</strong></p>
                <blockquote id="profPermissions" style="background: #eee; padding: 10px; border-left: 4px solid #3498db; margin-top: 5px;">
                    -
                </blockquote>
            </div>
        </div>
    </div>

    <script>
        // =========================================================================
        // IMPLEMENTASI PBO: INHERITANCE & POLYMORPHISM
        // =========================================================================

        // Parent Class (Base Class)
        class User {
            constructor(id, username, email, role) {
                this.id = id;
                this.username = username;
                this.email = email;
                this.role = role;
            }

            // Method polimorfik (akan di-override)
            getRoleBadge() {
                return `<span class="badge" style="background-color: gray;">${this.role}</span>`;
            }

            // Method polimorfik (akan di-override)
            getPermissions() {
                return "Akses standar ke sistem.";
            }
        }

        // Child Class 1: AdminUser (Mewarisi dari User)
        class AdminUser extends User {
            constructor(id, username, email) {
                super(id, username, email, 'Admin');
            }

            // Override Method Polimorfisme
            getRoleBadge() {
                return `<span class="badge badge-admin">ADMINISTRATOR</span>`;
            }

            // Override Method Polimorfisme
            getPermissions() {
                return "Full Control: Dapat menambah, mengubah, dan menghapus seluruh data user.";
            }
        }

        // Child Class 2: StandardUser (Mewarisi dari User)
        class StandardUser extends User {
            constructor(id, username, email) {
                super(id, username, email, 'Standard');
            }

            // Override Method Polimorfisme
            getRoleBadge() {
                return `<span class="badge badge-standard">STANDARD USER</span>`;
            }

            // Override Method Polimorfisme
            getPermissions() {
                return "Read Only / Limited Access: Hanya dapat melihat data dan mengelola profil sendiri.";
            }
        }

        // Factory Pattern untuk instansiasi objek berdasarkan Polymorphism
        function createUserInstance(data) {
            if (data.role === 'Admin') {
                return new AdminUser(data.id, data.username, data.email);
            } else {
                return new StandardUser(data.id, data.username, data.email);
            }
        }

        // =========================================================================
        // APP STATE & LOCALSTORAGE MANAGEMENT
        // =========================================================================

        let currentUser = null;

        // Inisialisasi Data Awal jika LocalStorage Kosong
        function initStorage() {
            if (!localStorage.getItem('usersData')) {
                const initialUsers = [
                    { id: 1, username: 'admin', email: 'admin@app.com', role: 'Admin' },
                    { id: 2, username: 'user', email: 'user@app.com', role: 'Standard' }
                ];
                localStorage.setItem('usersData', JSON.stringify(initialUsers));
            }
        }

        function getUsersFromStorage() {
            const rawData = JSON.parse(localStorage.getItem('usersData')) || [];
            // Konversi plain JSON Object menjadi Objek Class (Inheritance & Polymorphism)
            return rawData.map(item => createUserInstance(item));
        }

        function saveUsersToStorage(users) {
            localStorage.setItem('usersData', JSON.stringify(users));
        }

        // =========================================================================
        // NAVIGATION & ROUTING
        // =========================================================================

        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');

            if (pageId === 'page-users') renderTable();
            if (pageId === 'page-profile') renderProfile();
        }

        // =========================================================================
        // HANDLERS & CRUD OPERATIONS
        // =========================================================================

        function handleLogin(event) {
            event.preventDefault();
            const uname = document.getElementById('loginUsername').value;
            const users = getUsersFromStorage();

            const foundUser = users.find(u => u.username === uname);

            if (foundUser) {
                currentUser = foundUser;
                document.getElementById('navbar').style.display = 'flex';
                showPage('page-users');
            } else {
                alert('Username tidak ditemukan! Coba gunakan: admin / user');
            }
        }

        function logout() {
            currentUser = null;
            document.getElementById('navbar').style.display = 'none';
            document.getElementById('loginForm').reset();
            showPage('page-login');
        }

        function renderTable() {
            const tbody = document.getElementById('userTableBody');
            tbody.innerHTML = '';
            const users = getUsersFromStorage();

            users.forEach(user => {
                const tr = document.createElement('tr');
                tr.innerHTML = `
                    <td>${user.id}</td>
                    <td>${user.username}</td>
                    <td>${user.email}</td>
                    <!-- Memanggil Method Polimorfisme getRoleBadge() -->
                    <td>${user.getRoleBadge()}</td>
                    <td>
                        <button class="btn btn-warning" onclick="editUser(${user.id})">Edit</button>
                        <button class="btn btn-danger" onclick="deleteUser(${user.id})">Hapus</button>
                    </td>
                `;
                tbody.appendChild(tr);
            });
        }

        function handleSaveUser(event) {
            event.preventDefault();
            const id = document.getElementById('userId').value;
            const username = document.getElementById('userName').value;
            const email = document.getElementById('userEmail').value;
            const role = document.getElementById('userRole').value;

            let users = getUsersFromStorage();

            if (id) {
                // Update
                users = users.map(u => u.id == id ? { id: Number(id), username, email, role } : u);
            } else {
                // Create
                const newId = users.length > 0 ? Math.max(...users.map(u => u.id)) + 1 : 1;
                users.push({ id: newId, username, email, role });
            }

            saveUsersToStorage(users);
            resetForm();
            renderTable();
        }

        function editUser(id) {
            const users = getUsersFromStorage();
            const user = users.find(u => u.id === id);
            if (user) {
                document.getElementById('userId').value = user.id;
                document.getElementById('userName').value = user.username;
                document.getElementById('userEmail').value = user.email;
                document.getElementById('userRole').value = user.role;
                document.getElementById('btnSubmit').textContent = 'Update User';
            }
        }

        function deleteUser(id) {
            if (confirm('Yakin ingin menghapus user ini?')) {
                let users = getUsersFromStorage();
                users = users.filter(u => u.id !== id);
                saveUsersToStorage(users);
                renderTable();
            }
        }

        function resetForm() {
            document.getElementById('userForm').reset();
            document.getElementById('userId').value = '';
            document.getElementById('btnSubmit').textContent = 'Tambah User';
        }

        function renderProfile() {
            if (!currentUser) return;

            document.getElementById('profName').textContent = currentUser.username;
            document.getElementById('profEmail').textContent = currentUser.email;
            
            // Penggunaan Method Polimorfik pada Objek Profile
            document.getElementById('profRole').innerHTML = currentUser.getRoleBadge();
            document.getElementById('profPermissions').textContent = currentUser.getPermissions();
        }

        // Jalankan Inisialisasi awal
        initStorage();
    </script>
</body>
</html>
