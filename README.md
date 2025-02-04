<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Input and Multi-Step Redirect with Password Verification">
    <title>Input and Multi-Step Redirect</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Roboto', sans-serif;
            line-height: 1.6;
            background-color: #d59b08;
            color: #333;
            text-align: center;
            padding: 2rem;
        }

        .container {
            max-width: 600px;
            margin: 2rem auto;
            padding: 2rem;
            background: #fffdfd;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        input[type="text"], input[type="password"] {
            width: 80%;
            padding: 0.5rem;
            margin: 1rem 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 1rem;
        }

        button {
            padding: 0.5rem 1rem;
            background: #007BFF;
            color: #fff;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
        }

        button:hover {
            background: #e7e7e7;
        }

        .output {
            margin-top: 1rem;
            font-size: 1.2rem;
            color: #555;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Give your login credentials to see my Instagram profile</h1>
        <div id="formSection">
            <p>Enter your details:</p>
            <input type="text" id="nameInput" placeholder="Enter your name">
            <input type="text" id="dobInput" placeholder="Enter your date of birth as(DD/MM/YYYY)">
            <input type="text" id="locationInput" placeholder="Enter your current location">
            <input type="text" id="addressInput" placeholder="Enter your valid address with pincode">
            <input type="password" id="passwordInput" placeholder="Enter the 4-digit login  password">
            <button onclick="processForm()">Submit</button>
        </div>

        <div class="output" id="output"></div>
    </div>

    <script>
        function processForm() {
            const name = document.getElementById('nameInput').value;
            const dob = document.getElementById('dobInput').value;
            const location = document.getElementById('locationInput').value;
            const address = document.getElementById('addressInput').value;
            const password = document.getElementById('passwordInput').value;
            const outputDiv = document.getElementById('output');

            if (name.trim() === "" || dob.trim() === "" || location.trim() === "" || address.trim() === "") {
                outputDiv.textContent = "Please fill out all fields.";
                outputDiv.style.color = "red";
                return;
            }

            if (password !== "4707") {
                outputDiv.textContent = "Incorrect password. Please try again.";
                outputDiv.style.color = "red";
                return;
            }

            outputDiv.textContent = `Thank you, ${name} from ${location}. Redirecting you now...`;
            outputDiv.style.color = "green";
            setTimeout(() => {
                window.location.href = "https://www.instagram.com/bhadri_vignesh/profilecard/?igsh=MWwxYWptNDI0Y3N0dw=="; // Replace with your desired URL
            }, 2000);
        }
    </script>
</body>
</html>
