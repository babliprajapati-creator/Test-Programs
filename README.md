#Welcome to Student Management System Created By Babli Kumari
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>Student Management System</title>

    <link rel="stylesheet" href="style.css">

</head>


<body>

    <!-- HEADER -->

    <header>

        <h1>Student Management System</h1>

        <p>Student Management Dashboard</p>

    </header>


    <!-- MAIN CONTAINER -->

    <div class="container">


        <!-- SIDEBAR -->

        <aside class="sidebar">

            <h2>Dashboard</h2>


            <button onclick="showPage('dashboard')">
                🏠 Dashboard
            </button>


            <button onclick="showPage('addStudent')">
                ➕ Add Student
            </button>


            <button onclick="showPage('students')">
                👨‍🎓 View Students
            </button>


            <button onclick="showPage('search')">
                🔍 Search Student
            </button>


            <button onclick="showPage('update')">
                ✏️ Update Student
            </button>


            <button onclick="showPage('delete')">
                🗑️ Delete Student
            </button>


            <button onclick="showPage('attendance')">
                📅 Attendance
            </button>


            <button onclick="showPage('marks')">
                📊 Marks & Result
            </button>

        </aside>



        <!-- CONTENT -->

        <main class="content">


            <!-- ========================= -->
            <!-- DASHBOARD -->
            <!-- ========================= -->

            <section id="dashboard"
                     class="page">

                <h2>Dashboard</h2>


                <div class="cards">


                    <!-- TOTAL STUDENTS -->

                    <div class="card">

                        <h3>👨‍🎓 Total Students</h3>

                        <p id="totalStudents">0</p>

                    </div>


                    <!-- AVERAGE ATTENDANCE -->

                    <div class="card">

                        <h3>📅 Average Attendance</h3>

                        <p id="averageAttendance">0%</p>

                    </div>


                    <!-- AVERAGE MARKS -->

                    <div class="card">

                        <h3>📊 Average Marks</h3>

                        <p id="averageMarks">0</p>

                    </div>


                    <!-- PASS STUDENTS -->

                    <div class="card">

                        <h3>✅ Pass Students</h3>

                        <p id="passStudents">0</p>

                    </div>


                    <!-- FAIL STUDENTS -->

                    <div class="card">

                        <h3>❌ Fail Students</h3>

                        <p id="failStudents">0</p>

                    </div>


                </div>

            </section>



            <!-- ========================= -->
            <!-- ADD STUDENT -->
            <!-- ========================= -->

            <section id="addStudent"
                     class="page"
                     style="display:none;">

                <h2>Add Student</h2>


                <form id="studentForm">


                    <label>Student ID</label>

                    <input type="number"
                           id="studentId"
                           required>


                    <label>Student Name</label>

                    <input type="text"
                           id="studentName"
                           required>


                    <label>Course</label>

                    <input type="text"
                           id="course"
                           required>


                    <label>Semester</label>

                    <select id="semester"
                            required>

                        <option value="">
                            Select Semester
                        </option>

                        <option value="1">1</option>

                        <option value="2">2</option>

                        <option value="3">3</option>

                        <option value="4">4</option>

                        <option value="5">5</option>

                        <option value="6">6</option>

                    </select>


                    <br><br>


                    <button type="submit">

                        Save Student

                    </button>


                </form>

            </section>



            <!-- ========================= -->
            <!-- VIEW STUDENTS -->
            <!-- ========================= -->

            <section id="students"
                     class="page"
                     style="display:none;">

                <h2>Student Records</h2>


                <table border="1"
                       cellpadding="10"
                       width="100%">


                    <thead>

                        <tr>

                            <th>Student ID</th>

                            <th>Name</th>

                            <th>Course</th>

                            <th>Semester</th>

                            <th>Attendance</th>

                            <th>Marks</th>

                            <th>Action</th>

                        </tr>

                    </thead>


                    <tbody id="studentTableBody">

                    </tbody>


                </table>

            </section>



            <!-- ========================= -->
            <!-- SEARCH STUDENT -->
            <!-- ========================= -->

            <section id="search"
                     class="page"
                     style="display:none;">

                <h2>Search Student</h2>


                <input type="number"
                       id="searchId"
                       placeholder="Enter Student ID">


                <button type="button"
                        onclick="searchStudent()">

                    Search

                </button>


                <div id="searchResult"></div>

            </section>



            <!-- ========================= -->
            <!-- UPDATE STUDENT -->
            <!-- ========================= -->

            <section id="update"
                     class="page"
                     style="display:none;">

                <h2>Update Student</h2>


                <label>Student ID</label>

                <input type="number"
                       id="updateId"
                       placeholder="Enter Student ID">


                <br><br>


                <label>New Student Name</label>

                <input type="text"
                       id="updateName"
                       placeholder="Enter New Name">


                <br><br>


                <label>New Course</label>

                <input type="text"
                       id="updateCourse"
                       placeholder="Enter New Course">


                <br><br>


                <label>New Semester</label>

                <select id="updateSemester">

                    <option value="">
                        Select Semester
                    </option>

                    <option value="1">1</option>

                    <option value="2">2</option>

                    <option value="3">3</option>

                    <option value="4">4</option>

                    <option value="5">5</option>

                    <option value="6">6</option>

                </select>


                <br><br>


                <button type="button"
                        onclick="updateStudent()">

                    Update Student

                </button>


                <div id="updateResult"></div>

            </section>



            <!-- ========================= -->
            <!-- DELETE STUDENT -->
            <!-- ========================= -->

            <section id="delete"
                     class="page"
                     style="display:none;">

                <h2>Delete Student</h2>


                <label>Student ID</label>

                <input type="number"
                       id="deleteId"
                       placeholder="Enter Student ID">


                <br><br>


                <button type="button"
                        onclick="deleteStudent()">

                    Delete Student

                </button>


                <div id="deleteResult"></div>

            </section>



            <!-- ========================= -->
            <!-- ATTENDANCE -->
            <!-- ========================= -->

            <section id="attendance"
                     class="page"
                     style="display:none;">

                <h2>Student Attendance</h2>


                <label>Student ID</label>

                <input type="number"
                       id="attendanceId"
                       placeholder="Enter Student ID">


                <br><br>


                <label>Attendance (%)</label>

                <input type="number"
                       id="attendanceValue"
                       min="0"
                       max="100"
                       placeholder="Enter Attendance">


                <br><br>


                <button type="button"
                        onclick="saveAttendance()">

                    Save Attendance

                </button>


                <div id="attendanceResult"></div>

            </section>



            <!-- ========================= -->
            <!-- MARKS & RESULT -->
            <!-- ========================= -->

            <section id="marks"
                     class="page"
                     style="display:none;">

                <h2>Marks & Result</h2>


                <label>Student ID</label>

                <input type="number"
                       id="marksId"
                       placeholder="Enter Student ID">


                <br><br>


                <label>Marks</label>

                <input type="number"
                       id="marksValue"
                       min="0"
                       max="100"
                       placeholder="Enter Marks">


                <br><br>


                <button type="button"
                        onclick="saveMarks()">

                    Generate Result

                </button>


                <div id="marksResult"></div>

            </section>


        </main>

    </div>



    <!-- JAVASCRIPT -->

    <script src="script.js"></script>


</body>

</html>
