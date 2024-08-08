First, I downloaded the XAMPP program.To connect with the Database, and I added two columns in PhPMyAdmin https://demo.phpmyadmin.net/master-config/public/ , the first column is detect, to detect people, and the second column is the date, which will record the person with the date.

<img width="571" alt="q1" src="https://github.com/user-attachments/assets/1b3cdf5e-9267-429f-8ac9-36e184f9eb55">

<img width="630" alt="q2" src="https://github.com/user-attachments/assets/02f7376b-e829-427a-8a57-9d22c2e4a0cb">

And by using this code 
<?php

$detect = $_GET["detect"]; 

$servername = "localhost";
$username = "root";
$password = "";
$dbname = "robot";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully\n";

$date = date("Y/m/d"); //get system date

$sql = "INSERT INTO ultrasonic (detect, date) VALUES ('$detect' , '$date');";

if ($conn->query($sql) === TRUE) {
  echo "New record created successfully";
} else {
  echo "Error: " . $sql . "<br>" . $conn->error;
}

$conn->close();
?>

The database is connected to an ultrasonic sensor, every detection by the ultrasound sensor will add one person.

<img width="525" alt="q3" src="https://github.com/user-attachments/assets/dd1edfb9-affb-49f8-8454-324497816b86">

This simulation  was using https://wokwi.com/

<img width="264" alt="q4" src="https://github.com/user-attachments/assets/18744404-0ca7-4927-9503-68c7b3908e68">

  Output
