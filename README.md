<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Registration</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background: #f2f2f2;
            margin: 0;
            padding: 30px;
        }

        .container {
            max-width: 800px;
            margin: auto;
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px #ccc;
        }

        h1 {
            text-align: center;
            margin-bottom: 25px;
        }

        .row {
            display: flex;
            gap: 20px;
            margin-bottom: 18px;
        }

        .field {
            flex: 1;
        }

        label {
            display: block;
            margin-bottom: 6px;
            font-weight: bold;
        }

        input,
        select,
        textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 15px;
        }

        textarea {
            resize: vertical;
        }

        .gender {
            display: flex;
            gap: 20px;
            padding-top: 10px;
        }

        .gender label {
            font-weight: normal;
        }

        .gender input {
            width: auto;
        }

        button {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 5px;
            background: #333;
            color: white;
            font-size: 17px;
            cursor: pointer;
        }

        button:hover {
            background: #555;
        }

        #message {
            text-align: center;
            margin-top: 15px;
            font-weight: bold;
        }

        @media (max-width: 600px) {
            .row {
                flex-direction: column;
                gap: 15px;
            }
        }
    </style>
</head>

<body>

<div class="container">

    <h1>Student Registration Form</h1>

    <form id="studentForm">

        <div class="row">
            <div class="field">
                <label>Full Name</label>
                <input type="text" id="name" placeholder="Enter your name" required>
            </div>

            <div class="field">
                <label>Email</label>
                <input type="email" id="email" placeholder="Enter your email" required>
            </div>
        </div>

        <div class="row">
            <div class="field">
                <label>Phone Number</label>
                <input type="tel" id="phone" placeholder="Enter phone number"
                       pattern="[0-9]{10}" required>
            </div>

            <div class="field">
                <label>Date of Birth</label>
                <input type="date" id="dob" required>
            </div>
        </div>

        <div class="row">
            <div class="field">
                <label>Gender</label>

                <div class="gender">
                    <label>
                        <input type="radio" name="gender" value="Male" required>
                        Male
                    </label>

                    <label>
                        <input type="radio" name="gender" value="Female">
                        Female
                    </label>

                    <label>
                        <input type="radio" name="gender" value="Other">
                        Other
                    </label>
                </div>
            </div>
        </div>

        <div class="row">
            <div class="field">
                <label>College Name</label>
                <input type="text" id="college" placeholder="Enter college name" required>
            </div>

            <div class="field">
                <label>Student ID / Roll Number</label>
                <input type="text" id="roll" placeholder="Enter roll number" required>
            </div>
        </div>

        <div class="row">
            <div class="field">
                <label>Course</label>

                <select id="course" required>
                    <option value="">Select Course</option>
                    <option>B.Tech</option>
                    <option>B.Sc</option>
                    <option>BCA</option>
                    <option>M.Tech</option>
                    <option>MCA</option>
                    <option>MBA</option>
                </select>
            </div>

            <div class="field">
                <label>Branch</label>

                <select id="branch" required>
                    <option value="">Select Branch</option>
                    <option>CSE</option>
                    <option>IT</option>
                    <option>ECE</option>
                    <option>EEE</option>
                    <option>MECH</option>
                    <option>CIVIL</option>
                </select>
            </div>
        </div>

        <div class="row">
            <div class="field">
                <label>Year</label>

                <select id="year" required>
                    <option value="">Select Year</option>
                    <option>1st Year</option>
                    <option>2nd Year</option>
                    <option>3rd Year</option>
                    <option>4th Year</option>
                </select>
            </div>

            <div class="field">
                <label>Semester</label>

                <select id="semester" required>
                    <option value="">Select Semester</option>
                    <option>1st Semester</option>
                    <option>2nd Semester</option>
                    <option>3rd Semester</option>
                    <option>4th Semester</option>
                    <option>5th Semester</option>
                    <option>6th Semester</option>
                    <option>7th Semester</option>
                    <option>8th Semester</option>
                </select>
            </div>
        </div>

        <div class="row">
            <div class="field">
                <label>Skills</label>
                <input type="text" id="skills"
                       placeholder="Example: Python, Java, SQL">
            </div>

            <div class="field">
                <label>Resume</label>
                <input type="file" id="resume">
            </div>
        </div>

        <div class="row">
            <div class="field">
                <label>Address</label>
                <textarea id="address" rows="4"
                          placeholder="Enter your address" required></textarea>
            </div>
        </div>

        <div class="row">
            <div class="field">
                <label>Password</label>
                <input type="password" id="password"
                       placeholder="Create password" required>
            </div>

            <div class="field">
                <label>Confirm Password</label>
                <input type="password" id="confirmPassword"
                       placeholder="Confirm password" required>
            </div>
        </div>

        <button type="submit">Register</button>

        <p id="message"></p>

    </form>

</div>


<script>

    document.getElementById("studentForm").addEventListener("submit", function(event) {

        event.preventDefault();

        let password = document.getElementById("password").value;
        let confirmPassword = document.getElementById("confirmPassword").value;
        let message = document.getElementById("message");

        if (password !== confirmPassword) {

            message.innerText = "❌ Passwords do not match!";
            message.style.color = "red";

            return;
        }

        message.innerText = "✅ Registration Successful!";
        message.style.color = "green";

        document.getElementById("studentForm").reset();

    });

</script>

</body>
</html>
