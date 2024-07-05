<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TRC: Therapy for Kids Ages 6-13</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: blue;
      color: #fff;
      padding: 10px 0;
      text-align: center;
    }
    nav {
      text-align: center;
      margin-bottom: 20px;
    }
    nav a {
      text-decoration: none;
      color: #333;
      padding: 10px 20px;
      margin: 0 5px;
      border-radius: 5px;
      background-color: #f2f2f2;
    }
    nav a:hover {
      background-color: #ddd;
    }
    .container {
      width: 80%;
      margin: auto;
      overflow: hidden;
      padding: 20px;
    }
    .services {
      margin-top: 20px;
    }
    .service {
      margin-bottom: 20px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .about {
      margin-top: 20px;
    }
    .contact {
      margin-top: 20px;
      text-align: center;
    }
    form {
      margin-top: 20px;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 5px;
      background-color: #f9f9f9;
    }
    label {
      display: block;
      margin-bottom: 10px;
    }
    input[type="text"],
    input[type="email"],
    input[type="date"],
    input[type="submit"] {
      width: 100%;
      padding: 8px;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 4px;
      box-sizing: border-box;
    }
    .error {
      color: red;
    }
  </style>
</head>
<body>

<header>
  <h1>TRC: Therapy for Kids Ages 6-13</h1>
</header>

<nav>
  <a href="#home">Home</a>
  <a href="#services">Services</a>
  <a href="#about">About Us</a>
  <a href="#contact">Contact</a>
</nav>

<section id="home" class="container">
  <h2>Welcome to TRC</h2>
  <p>We specialize in providing therapy services for children between the ages of 6 and 13, helping them overcome various challenges and thrive.</p>
  <p>Our team of dedicated professionals is committed to creating a safe and supportive environment for your child's growth and development.</p>
</section>

<section id="services" class="container services">
  <h2>Our Services</h2>
  <div class="service">
    <h3>Individual Therapy</h3>
    <p>Customized therapy sessions tailored to meet the unique needs of your child.</p>
  </div>
  <!-- Add more service sections as needed -->
</section>

<section id="about" class="container about">
  <h2>About Us</h2>
  <p>TRC (Therapy for Kids Ages 6-13) is dedicated to providing comprehensive therapeutic services for children in a nurturing and supportive environment.</p>
  <p>Our therapists are highly trained and experienced in working with children, ensuring that each therapy session is effective and beneficial.</p>
</section>

<section id="contact" class="container contact">
  <h2>Contact Us</h2>
  <p>If you have any questions or would like to schedule an appointment, please contact us:</p>
  <p>Email: trc.for.everyone.in.life@gmail.com</p>
  <p>Phone: +81 80 8025 1966</p>
</section>

<section class="container">
</body>
</html>

 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Booking Form</title>
</head>
<body>
    <h2>Booking Form</h2>
    <form action="send_email.php" method="POST">
        <label for="name">Your Name:</label><br>
        <input type="text" id="name" name="name" required><br><br>
        
        <label for="email">Your Email:</label><br>
        <input type="email" id="email" name="email" required><br><br>
        
        <label for="phone">Phone Number:</label><br>
        <input type="tel" id="phone" name="phone" required><br><br>
        
        <label for="message">Message:</label><br>
        <textarea id="message" name="message" rows="4" required></textarea><br><br>
        
        <input type="submit" value="Submit">
    </form>

 <footer>
        <p>&copy; 2024 Your Company Name. All rights reserved.</p>
    </footer>
</body>
</html>
function sendEmail(name, email, phone, message) {
    // Construct email content
    let emailContent = {
        name: name,
        email: email,
        phone: phone,
        message: message
    };

    // Example using Fetch API to send data to a server-side endpoint
    fetch('http://localhost:3000/sendEmail', { // Replace with your actual server URL
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(emailContent)
    })
    .then(response => {
        if (response.ok) {
            return response.json();
        }
        throw new Error('Network response was not ok.');
    })
    .then(data => {
        console.log('Email sent successfully:', data);
        alert('Thank you! Your booking has been received.');
        // Optionally, redirect or perform other actions after successful submission
    })
    .catch(error => {
        console.error('Error sending email:', error);
        alert('Oops! Something went wrong. Please try again later.');
    });
}

// Example of handling form submission
document.getElementById('bookingForm').addEventListener('submit', function(event) {
    event.preventDefault();

    // Collect form data
    let name = document.getElementById('name').value;
    let email = document.getElementById('email').value;
    let phone = document.getElementById('phone').value;
    let message = document.getElementById('message').value;

    // Call sendEmail function with form data
    sendEmail(name, email, phone, message);
});

