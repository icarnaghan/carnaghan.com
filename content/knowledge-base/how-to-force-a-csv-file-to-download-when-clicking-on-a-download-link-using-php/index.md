---
author: "icarnaghan"
title: "How to force a CSV file to download when clicking on a download link using PHP"
date: 2018-03-22
---

**Example**: We have a **CSV** file called **example.csv** we want users to **download** to use as a template. Now some **browsers** will display the contents of the file instead of asking users to **download** the file. What we want to do is to force the **download**instead of displaying the contents in the **browser**.

- Create a new **PHP** file called '**download.php**'
- Open the file for editing
- Copy the code below into the '**download.php**' file {codecitation style="brush: PHP;"} header('Content-Type: application/csv'); //Outputting the file as a csv file header('Content-Disposition: attachment; filename=example.csv'); //Defining the name of the file and suggesting the browser to offer a 'Save to disk ' option header('Pragma: no-cache');
    
    echo readfile('example.csv'); //Reading the contents of the file {/codecitation}
- Now on the page where you want the user to click on the link to **download** the file add the following code {codecitation style="brush: HTML;"} <a href="/download.php">Click here to download an example of the "CSV" file</a> {/codecitation}
- Now everytime the user clicks on the link the browser won't display the contents but will offer to **download** the file
