<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "amp_test";

// Create connection
$conn = mysqli_connect($servername, $username, $password, $dbname);
// Check connection
if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}
$sql = "SELECT project_template.template_id from project_template INNER JOIN template_info ON project_template.template_id=template_info.template_id";

$result = mysqli_query($conn, $sql);
$i=1;
if (mysqli_num_rows($result) > 0) {
    // output data of each row
    while($row = mysqli_fetch_assoc($result)) {
    $templateId = $row['template_id'];
    $template_text = $conn->query("SELECT template_text FROM template_info WHERE template_id='$templateId';");
    $template_text = mysqli_fetch_assoc($template_text)['template_text'];
    $template_text = escapeSequence($template_text);
    echo 
    die;
    if ($conn->query("UPDATE project_template SET user_template_text = '$template_text' where template_id='$templateId';") === TRUE) {
        echo "New record updated successfully and id of template is ".$templateId." and record is ".$i++."<br>";

    }
    else
    {
        echo "New record not updated successfully and id of template is ".$templateId." and record is ".$i++."<br>";
    }

} 
}
else {
    echo "0 results";
}
function escapeSequence($html_data)
{
    return $html_data = str_replace("'", "\"", $html_data);
}
mysqli_close($conn);


?>
