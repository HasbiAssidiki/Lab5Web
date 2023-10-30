# Lab5Web
```
Nama : Hasbi Assidiki
Nim  : 312210448
Kelas: TI.22.A4
```
Tugas Membuat script untuk melakukan validasi pada isian form.
- Script HTML
``` html
<!DOCTYPE html>
<html>
<head>
    <title>Validasi Form</title>
    <link rel="stylesheet" type="text/css" href="style2.css">
</head>
<body>
    <form onsubmit="return validateForm()" method="post">
        <h2>Formulir</h2>
        <div class="error" id="nameError"></div>
        Nama: <input type="text" name="name"><br>
        <div class="error" id="emailError"></div>
        Email: <input type="text" name="email"><br>
        <input type="submit" value="Kirim">
    </form>

    <script>
        function validateForm() {
            const name = document.forms[0].name.value;
            const email = document.forms[0].email.value;

            if (name === "") {
                document.getElementById("nameError").innerHTML = "Nama harus diisi";
                return false;
            } else {
                document.getElementById("nameError").innerHTML = "";
            }

            if (email === "") {
                document.getElementById("emailError").innerHTML = "Email harus diisi";
                return false;
            } else {
                document.getElementById("emailError").innerHTML = "";
            }

            const emailPattern = /^\w+@[a-zA-Z_]+?\.[a-zA-Z]{2,3}$/;
            if (!email.match(emailPattern)) {
                document.getElementById("emailError").innerHTML = "Email tidak valid";
                return false;
            } else {
                document.getElementById("emailError").innerHTML = "";
            }

            return true;
        }
    </script>
</body>
</html>
```
- Style CSS
``` css
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f4f4f4;
    margin: 0;
}
form {
    background-color: #fff;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
}
input[type="text"], input[type="email"], input[type="submit"] {
    width: calc(100% - 22px);
    padding: 10px;
    margin: 5px 0;
    border: 1px solid #ccc;
    border-radius: 3px;
    box-sizing: border-box;
}
input[type="submit"] {
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
}
input[type="submit"]:hover {
    background-color: #45a049;
}
.error {
    color: red;
    font-size: 14px;
    margin-bottom: 5px;
}

```
- Hasil
    
  ![O12](https://github.com/HasbiAssidiki/Lab5Web/assets/115614317/13739c65-8f81-4e0a-a8cc-1ed298c021b5)  
