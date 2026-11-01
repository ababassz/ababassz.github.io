# ababassz.github.io

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Website</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f2f5;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }

        .container {
            background-color: white;
            padding: 35px;
            border-radius: 15px;
            text-align: center;
            width: 300px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        h1 {
            color: #333;
        }

        p {
            color: #666;
        }

        input {
            width: 100%;
            padding: 12px;
            margin: 15px 0;
            border: 1px solid #ccc;
            border-radius: 6px;
            box-sizing: border-box;
            font-size: 16px;
        }

        button {
            width: 100%;
            padding: 12px;
            background-color: #2563eb;
            color: white;
            border: none;
            border-radius: 6px;
            font-size: 16px;
            cursor: pointer;
        }

        button:hover {
            background-color: #1d4ed8;
        }

        #result {
            margin-top: 20px;
            font-weight: bold;
            color: #2563eb;
        }
    </style>
</head>

<body>

    <div class="container">
        <h1>Welcome to My Website!</h1>

        <p>What is your name?</p>

        <input
            type="text"
            id="name"
            placeholder="Enter your name"
        >

        <button onclick="submitName()">Submit</button>

        <p id="result"></p>
    </div>

    <script>
        function submitName() {
            let name = document.getElementById("name").value;

            if (name.trim() === "") {
                document.getElementById("result").textContent =
                    "Please enter your name!";
            } else {
                document.getElementById("result").textContent =
                    "Hello, " + name + "! Welcome!";
            }
        }
    </script>

</body>
</html>
